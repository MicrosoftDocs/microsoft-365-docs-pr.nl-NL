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
ms.openlocfilehash: 1c8d61aee9afb332a8426890560ad221a9c87c7d
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218791"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-103">Anti-phishingbeleid configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db8a0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="db8a0-104">**Applies to**</span></span>
- [<span data-ttu-id="db8a0-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="db8a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db8a0-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="db8a0-107">Anti-phishingbeleid in [Microsoft Defender voor Office 365](defender-for-office-365.md) kan uw organisatie helpen beschermen tegen kwaadaardige phishingaanvallen op basis van imitaties en andere soorten phishingaanvallen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="db8a0-108">Zie [Anti-phishingbeveiliging](anti-phishing-protection.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in Exchange Online Protection (EOP) en anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="db8a0-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="db8a0-109">Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="db8a0-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="db8a0-110">Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="db8a0-111">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="db8a0-112">U kunt anti-phishingbeleid configureren in het Beveiligings- & compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db8a0-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="db8a0-113">Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor informatie over het configureren van de meer beperkte anti-phishingbeleidsregels die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen organisaties zonder Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="db8a0-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="db8a0-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="db8a0-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="db8a0-115">**Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="db8a0-116">**De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="db8a0-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="db8a0-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="db8a0-118">Wanneer u een beleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="db8a0-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="db8a0-119">Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="db8a0-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="db8a0-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="db8a0-121">Wanneer u een beleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="db8a0-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="db8a0-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="db8a0-123">Zie de sectie Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren in de sectie Microsoft Defender voor [Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="db8a0-124">Elke Microsoft Defender voor Office 365-organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="db8a0-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="db8a0-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="db8a0-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="db8a0-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="db8a0-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="db8a0-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="db8a0-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="db8a0-129">Als u de beveiliging tegen phishing wilt verbeteren in Microsoft Defender voor Office 365, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="db8a0-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db8a0-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="db8a0-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db8a0-131">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="db8a0-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="db8a0-132">Als u rechtstreeks naar de **anti-phishingpagina van ATP** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="db8a0-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="db8a0-133">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db8a0-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="db8a0-134">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="db8a0-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="db8a0-135">Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="db8a0-136">Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="db8a0-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="db8a0-137">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="db8a0-138">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="db8a0-138">**Notes**:</span></span>

  - <span data-ttu-id="db8a0-139">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db8a0-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="db8a0-140">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="db8a0-141">De **rollengroep Alleen-weergeven in** [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="db8a0-142"><sup>\*</sup> In het & compliancecentrum kunnen gebruikers met alleen-lezen toegang de instellingen van aangepast anti-phishingbeleid bekijken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="db8a0-143">Alleen-lezen gebruikers kunnen de instellingen niet zien in het standaard anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="db8a0-144">Zie [Anti-phishingbeleid in Defender voor Office 365-instellingen](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)voor onze aanbevolen instellingen voor anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="db8a0-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="db8a0-145">Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="db8a0-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="db8a0-146">Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="db8a0-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-147">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid te maken in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db8a0-148">Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="db8a0-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="db8a0-149">Wanneer u een anti-phishingbeleid maakt, kunt u alleen de naam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="db8a0-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="db8a0-150">Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="db8a0-151">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-152">Klik op **de pagina Anti-phishing** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="db8a0-153">De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="db8a0-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="db8a0-154">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="db8a0-155">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="db8a0-156">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="db8a0-157">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="db8a0-158">Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="db8a0-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="db8a0-159">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="db8a0-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="db8a0-160">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="db8a0-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="db8a0-161">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="db8a0-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="db8a0-162">Klik **op Een voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-162">Click **Add a condition**.</span></span> <span data-ttu-id="db8a0-163">Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="db8a0-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="db8a0-164">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="db8a0-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="db8a0-165">**De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="db8a0-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="db8a0-166">**Het domein van de geadresseerde is:** hiermee geeft u geadresseerden op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="db8a0-167">Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="db8a0-168">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="db8a0-169">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="db8a0-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="db8a0-170">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="db8a0-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="db8a0-171">Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="db8a0-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="db8a0-172">Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="db8a0-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="db8a0-173">Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="db8a0-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="db8a0-174">Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="db8a0-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="db8a0-175">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="db8a0-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="db8a0-176">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="db8a0-177">Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="db8a0-178">U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="db8a0-179">Wanneer u klaar bent, klikt u op **Dit beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="db8a0-180">Klik **op OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="db8a0-181">Nadat u het anti-phishingbeleid met deze algemene instellingen hebt gemaakt, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-182">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid te wijzigen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db8a0-183">Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="db8a0-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="db8a0-184">Als u er nog niet bent, opent u het Beveiligingscentrum & compliancecentrum en gaat u naar Threat **management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-185">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="db8a0-186">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db8a0-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db8a0-187">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="db8a0-188">Als u in **een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="db8a0-189">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="db8a0-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="db8a0-190">Nadat u **in** een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling, maar  u kunt in elke volgorde binnen de pagina's springen en u kunt op Opslaan op een pagina klikken (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** pictogram Annuleren of Sluiten sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="db8a0-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="db8a0-191">**Beleidsinstelling:** Klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het [beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="db8a0-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="db8a0-192">**Naam**</span><span class="sxs-lookup"><span data-stu-id="db8a0-192">**Name**</span></span>
   - <span data-ttu-id="db8a0-193">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="db8a0-193">**Description**</span></span>
   - <span data-ttu-id="db8a0-194">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="db8a0-194">**Applied to**</span></span>
   - <span data-ttu-id="db8a0-195">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="db8a0-195">**Review your settings**</span></span>

   <span data-ttu-id="db8a0-196">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="db8a0-197">**Imitatie:** Klik op **Bewerken om** de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="db8a0-198">Deze instellingen zijn een voorwaarde voor het beleid dat vervalste afzenders identificeert om te zoeken (afzonderlijk of per domein) in het Van-adres van binnenkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="db8a0-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="db8a0-199">Zie Instellingen voor imitatie [in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="db8a0-200">**Gebruikers toevoegen om te beveiligen:** De standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-201">Als u deze wilt in- of uitschakelen,  schuift u de schakelknop naar **Aan** en klikt u vervolgens op de knop Gebruiker toevoegen die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="db8a0-202">Configureer **in het** flyout Gebruiker toevoegen dat wordt weergegeven de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="db8a0-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="db8a0-203">**E-mailadres**:</span><span class="sxs-lookup"><span data-stu-id="db8a0-203">**Email address**:</span></span>

       - <span data-ttu-id="db8a0-204">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="db8a0-205">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db8a0-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="db8a0-206">Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db8a0-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="db8a0-207">**Naam:** Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="db8a0-208">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="db8a0-209">Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="db8a0-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="db8a0-210">In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers opgeven (e-mailadressen van afzenders).</span><span class="sxs-lookup"><span data-stu-id="db8a0-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="db8a0-211">U kunt niet dezelfde beveiligde gebruiker opgeven in meerdere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="db8a0-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="db8a0-212">Gebruikersbeveiliging werkt niet als de afzender en geadresseerde eerder via e-mail hebben gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="db8a0-213">Als de afzender en geadresseerde nooit via e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.</span><span class="sxs-lookup"><span data-stu-id="db8a0-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="db8a0-214">**Domeinen toevoegen om te beveiligen:** Een of beide van de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="db8a0-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="db8a0-215">**Automatisch de domeinen opnemen die ik bezit:** De standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-216">Als u deze wilt in- of uitschakelen, schuift u de schakelknop naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db8a0-217">**Aangepaste domeinen opnemen:** de standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-218">Als u de knop wilt in- of  uitschakelen, schuift u de schakelknop naar **Aan** en typt u in het vak Domeinen toevoegen de domeinnaam (bijvoorbeeld contoso.com), drukt u op Enter en herhaalt u zo nodig.</span><span class="sxs-lookup"><span data-stu-id="db8a0-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="db8a0-219">U kunt maximaal 50 domeinen hebben in alle anti-phishingbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="db8a0-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="db8a0-220">**Acties**: Klik op **Bewerken**</span><span class="sxs-lookup"><span data-stu-id="db8a0-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="db8a0-221">**Als e-mail** wordt verzonden door een nagebootsde gebruiker: Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in Gebruikers toevoegen ter **bescherming:**</span><span class="sxs-lookup"><span data-stu-id="db8a0-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="db8a0-222">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="db8a0-223">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db8a0-224">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="db8a0-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db8a0-225">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="db8a0-226">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="db8a0-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db8a0-227">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="db8a0-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="db8a0-228">**Als e-mail** wordt verzonden door een nagebootsd domein: Configureer een van de volgende acties voor berichten waarin de vervalste afzender zich in een van de beveiligde domeinen die u hebt opgegeven in **Domeinen** toevoegen ter bescherming configureren:</span><span class="sxs-lookup"><span data-stu-id="db8a0-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="db8a0-229">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="db8a0-230">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db8a0-231">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="db8a0-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db8a0-232">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="db8a0-233">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="db8a0-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db8a0-234">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="db8a0-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="db8a0-235">Klik **op veiligheidstips voor imitatie in-** en configureren een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="db8a0-236">**Tip voor imiteerde gebruikers tonen:** De standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-237">Als u deze wilt in- of uitschakelen, schuift u de schakelknop naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db8a0-238">**Tip voor nagebootste domeinen tonen:** De standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-239">Als u deze wilt in- of uitschakelen, schuift u de schakelknop naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db8a0-240">**Tip voor ongebruikelijke tekens tonen:** De standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="db8a0-241">Als u deze wilt in- of uitschakelen, schuift u de schakelknop naar **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="db8a0-242">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="db8a0-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="db8a0-243">**Postvakintelligentie:**</span><span class="sxs-lookup"><span data-stu-id="db8a0-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="db8a0-244">**Postvakintelligentie inschakelen?**: De standaardwaarde is **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="db8a0-245">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="db8a0-246">**Postvakintelligentie inschakelen op basis van imitatiebeveiliging?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen is** **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="db8a0-247">Schakel deze instelling in om de actie op te geven die u moet ondernemen voor berichten voor imitatiedetecties van postvakinformatieresultaten.</span><span class="sxs-lookup"><span data-stu-id="db8a0-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="db8a0-248">In **Als e-mail wordt** verzonden door een nagebootsde gebruiker, kunt u een van de volgende acties opgeven (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="db8a0-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="db8a0-249">**Pas geen actie** toe: houd er rekening mee dat deze waarde hetzelfde resultaat heeft als het inschakelen van postvakinformatie inschakelen? maar postvakintelligentie op basis van  **imitatiebeveiliging inschakelen uitschakelen?**.</span><span class="sxs-lookup"><span data-stu-id="db8a0-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="db8a0-250">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db8a0-251">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="db8a0-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db8a0-252">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="db8a0-253">**Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="db8a0-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db8a0-254">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="db8a0-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="db8a0-255">**Vertrouwde afzenders en domeinen toevoegen:** geef uitzonderingen op voor het beleid:</span><span class="sxs-lookup"><span data-stu-id="db8a0-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="db8a0-256">**Vertrouwde afzenders:**</span><span class="sxs-lookup"><span data-stu-id="db8a0-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="db8a0-257">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="db8a0-258">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db8a0-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="db8a0-259">Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="db8a0-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="db8a0-260">**Vertrouwde domeinen:** Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op Enter en herhaal indien nodig.</span><span class="sxs-lookup"><span data-stu-id="db8a0-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="db8a0-261">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="db8a0-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="db8a0-262">U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="db8a0-263">U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="db8a0-264">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="db8a0-264">**Protected users**</span></span>
       - <span data-ttu-id="db8a0-265">**Beveiligde domeinen** \> **Domeinen opnemen die ik bezit**</span><span class="sxs-lookup"><span data-stu-id="db8a0-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="db8a0-266">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="db8a0-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="db8a0-267">**Postvakintelligentie**</span><span class="sxs-lookup"><span data-stu-id="db8a0-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="db8a0-268">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="db8a0-269">**Spoof:** Klik op **Bewerken** om spoofinformatie in of uit te schakelen, identiteitsgegevens van niet-nautische afzenders in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="db8a0-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="db8a0-270">Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="db8a0-271">Houd er rekening mee dat deze instellingen ook beschikbaar zijn in anti-phishingbeleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="db8a0-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="db8a0-272">**Instellingen voor spoofingfilter:** De standaardwaarde is **Aan** en u wordt aangeraden deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="db8a0-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="db8a0-273">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="db8a0-274">Zie Spoof [intelligence configureren in EOP voor meer informatie.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="db8a0-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="db8a0-275">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 gaat. u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="db8a0-276">Zie Verbeterde filtering [voor connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="db8a0-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="db8a0-277">**Functie Unauthenticated Sender inschakelen:** De standaardwaarde is **Aan.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="db8a0-278">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="db8a0-279">**Acties:** Geef de actie op die moet worden ondernomen voor berichten die niet worden vervalst:</span><span class="sxs-lookup"><span data-stu-id="db8a0-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="db8a0-280">**Als e-mail wordt verzonden door iemand die uw** domein niet mag vervalsen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="db8a0-281">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="db8a0-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="db8a0-282">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="db8a0-283">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="db8a0-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="db8a0-284">U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="db8a0-285">U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="db8a0-286">**Antispoofingbeveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="db8a0-287">**Functie Unauthenticated Sender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="db8a0-288">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="db8a0-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="db8a0-289">**Geavanceerde instellingen:** Klik op **Bewerken om** de geavanceerde phishingdrempels te configureren.</span><span class="sxs-lookup"><span data-stu-id="db8a0-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="db8a0-290">Zie Geavanceerde [phishingdrempels in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="db8a0-291">**Geavanceerde phishingdrempels:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="db8a0-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="db8a0-292">**1 - Standaard** (Dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="db8a0-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="db8a0-293">**2 - Agressief**</span><span class="sxs-lookup"><span data-stu-id="db8a0-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="db8a0-294">**3 - Agressiever**</span><span class="sxs-lookup"><span data-stu-id="db8a0-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="db8a0-295">**4 - Meest agressief**</span><span class="sxs-lookup"><span data-stu-id="db8a0-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="db8a0-296">**Uw instellingen controleren:** Klik op **Bewerken om** terug te gaan naar de **pagina Geavanceerde phishingdrempels.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="db8a0-297">Wanneer u klaar bent, klikt u **op Opslaan** op beide pagina's.</span><span class="sxs-lookup"><span data-stu-id="db8a0-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="db8a0-298">Bekijk de instellingen op **de \<Name\> pagina** Uw beleid bewerken en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-299">Gebruik het beveiligings- & compliancecentrum om het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 te wijzigen</span><span class="sxs-lookup"><span data-stu-id="db8a0-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db8a0-300">Het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 heeft de naam Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="db8a0-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="db8a0-301">Als u het standaard anti-phishingbeleid wilt wijzigen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="db8a0-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="db8a0-302">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-303">Klik op **de pagina Anti-phishing** op **Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="db8a0-304">De **pagina Uw beleid bewerken Office365 AntiPhish Default** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="db8a0-305">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="db8a0-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="db8a0-306">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="db8a0-306">**Impersonation**</span></span>
   - <span data-ttu-id="db8a0-307">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="db8a0-307">**Spoof**</span></span>
   - <span data-ttu-id="db8a0-308">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="db8a0-308">**Advanced settings**</span></span>

   <span data-ttu-id="db8a0-309">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="db8a0-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="db8a0-310">U kunt  de sectie Beleidsinstelling en -waarden  zien, maar er is geen koppeling Bewerken, dus u kunt de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (dit geldt voor alle geadresseerden)).</span><span class="sxs-lookup"><span data-stu-id="db8a0-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="db8a0-311">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="db8a0-312">U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="db8a0-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="db8a0-313">Controleer op **de pagina Uw beleid bewerken Office365 AntiPhish Default** uw instellingen en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-314">Aangepaste anti-phishingbeleidsregels in- of uitschakelen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db8a0-315">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-316">Let op de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="db8a0-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="db8a0-317">Schuif de schakelknop naar **Uit om** het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="db8a0-318">Schuif de schakelknop naar **Aan om** het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="db8a0-319">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-320">De prioriteit instellen van aangepast anti-phishingbeleid in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db8a0-321">Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="db8a0-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="db8a0-322">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="db8a0-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="db8a0-323">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="db8a0-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="db8a0-324">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="db8a0-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="db8a0-325">Aangepaste anti-phishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="db8a0-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="db8a0-326">Het standaard anti-phishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="db8a0-327">**Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="db8a0-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="db8a0-328">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="db8a0-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="db8a0-329">Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het Beveiligings- & Compliancecentrum).</span><span class="sxs-lookup"><span data-stu-id="db8a0-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="db8a0-330">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="db8a0-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="db8a0-331">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-332">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="db8a0-333">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db8a0-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db8a0-334">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="db8a0-335">Het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="db8a0-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="db8a0-336">Het aangepaste anti-phishingbeleid  met de laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="db8a0-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="db8a0-337">Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, hebben  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="db8a0-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="db8a0-338">Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="db8a0-339">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="db8a0-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-340">Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid weer te geven in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db8a0-341">Ga in & Beveiligingscentrum naar Threat **Management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-342">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="db8a0-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="db8a0-343">Selecteer een aangepast anti-phishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="db8a0-344">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db8a0-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="db8a0-345">Klik **op Standaardbeleid** om het standaardbeleid voor anti-phishing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="db8a0-346">Het **fly-out \<name\>** Beleid bewerken wordt weergegeven, waar u de instellingen en waarden kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-347">Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid te verwijderen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db8a0-348">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db8a0-349">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="db8a0-350">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="db8a0-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db8a0-351">Klik in **het \<name\> flyout** Beleid bewerken dat wordt weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="db8a0-352">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db8a0-353">Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="db8a0-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db8a0-354">Zoals eerder beschreven, bestaat een antispambeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="db8a0-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="db8a0-355">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="db8a0-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="db8a0-356">U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="db8a0-357">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="db8a0-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="db8a0-358">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="db8a0-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="db8a0-359">Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="db8a0-360">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="db8a0-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="db8a0-361">Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="db8a0-362">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="db8a0-363">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="db8a0-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="db8a0-364">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="db8a0-364">**Notes**:</span></span>

- <span data-ttu-id="db8a0-365">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="db8a0-366">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="db8a0-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="db8a0-367">U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="db8a0-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="db8a0-368">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="db8a0-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="db8a0-369">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="db8a0-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="db8a0-370">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum als u het beleid aan een anti-phish-regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="db8a0-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="db8a0-371">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="db8a0-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="db8a0-372">Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="db8a0-373">In dit voorbeeld wordt anti-phishbeleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="db8a0-374">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).</span><span class="sxs-lookup"><span data-stu-id="db8a0-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="db8a0-375">De beschrijving is: Het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="db8a0-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="db8a0-376">Hiermee wordt de beveiliging van organisatiedomeinen voor alle geaccepteerde domeinen en de bescherming van gerichte domeinen voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="db8a0-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="db8a0-377">Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker die u wilt beschermen tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="db8a0-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="db8a0-378">Hiermee schakelt u postvakintelligentie in.</span><span class="sxs-lookup"><span data-stu-id="db8a0-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="db8a0-379">Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.</span><span class="sxs-lookup"><span data-stu-id="db8a0-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="db8a0-380">Hiermee schakelt u veiligheidstips in.</span><span class="sxs-lookup"><span data-stu-id="db8a0-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="db8a0-381">Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="db8a0-382">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="db8a0-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="db8a0-383">Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="db8a0-384">In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="db8a0-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="db8a0-385">De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="db8a0-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="db8a0-386">De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="db8a0-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="db8a0-387">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="db8a0-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="db8a0-388">Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="db8a0-389">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="db8a0-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="db8a0-390">Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="db8a0-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db8a0-391">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="db8a0-392">Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="db8a0-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="db8a0-393">Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="db8a0-394">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="db8a0-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="db8a0-395">Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db8a0-396">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db8a0-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="db8a0-397">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="db8a0-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="db8a0-398">Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="db8a0-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="db8a0-399">Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="db8a0-400">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="db8a0-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="db8a0-401">Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="db8a0-402">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db8a0-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="db8a0-403">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="db8a0-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="db8a0-404">Wanneer u de naam van een anti-phishingbeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="db8a0-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="db8a0-405">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="db8a0-406">Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="db8a0-407">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="db8a0-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="db8a0-408">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="db8a0-409">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="db8a0-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="db8a0-410">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="db8a0-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="db8a0-411">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="db8a0-412">Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="db8a0-413">Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="db8a0-414">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="db8a0-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="db8a0-415">Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="db8a0-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="db8a0-416">U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="db8a0-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="db8a0-417">Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="db8a0-418">In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="db8a0-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db8a0-419">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="db8a0-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db8a0-420">Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="db8a0-421">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="db8a0-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="db8a0-422">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="db8a0-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="db8a0-423">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="db8a0-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="db8a0-424">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="db8a0-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="db8a0-425">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="db8a0-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="db8a0-426">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="db8a0-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="db8a0-427">Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="db8a0-428">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="db8a0-428">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="db8a0-429">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="db8a0-429">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="db8a0-430">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="db8a0-430">**Notes**:</span></span>

- <span data-ttu-id="db8a0-431">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="db8a0-432">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.</span><span class="sxs-lookup"><span data-stu-id="db8a0-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="db8a0-433">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="db8a0-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="db8a0-434">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="db8a0-435">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="db8a0-436">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="db8a0-437">Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="db8a0-438">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="db8a0-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="db8a0-439">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="db8a0-440">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db8a0-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="db8a0-441">In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db8a0-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db8a0-442">Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="db8a0-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="db8a0-443">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="db8a0-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="db8a0-444">Ga als volgt te werk om te controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="db8a0-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="db8a0-445">Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="db8a0-446">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="db8a0-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="db8a0-447">Ga als volgt te werk om meer details weer te geven:</span><span class="sxs-lookup"><span data-stu-id="db8a0-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="db8a0-448">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="db8a0-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="db8a0-449">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="db8a0-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="db8a0-450">Vervang in Exchange Online PowerShell door de naam van het beleid of de regel en voer de volgende \<Name\> opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="db8a0-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```