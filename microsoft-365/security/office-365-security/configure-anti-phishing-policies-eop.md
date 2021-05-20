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
ms.openlocfilehash: bc3c15d2a652e9acd3407ecb91fc99b7ef295c7e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537917"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="b9094-103">Antiphishingbeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="b9094-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b9094-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b9094-104">**Applies to**</span></span>
- [<span data-ttu-id="b9094-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b9094-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="b9094-106">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection(EOP) organisaties zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal anti-spoofing-functies bevat die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b9094-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="b9094-107">Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="b9094-108">Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="b9094-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="b9094-109">Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b9094-110">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b9094-111">Organisaties met Exchange Online-postvakken kunnen anti-phishingbeleid configureren in het Beveiligings- & compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9094-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="b9094-112">Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="b9094-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="b9094-113">Zie Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie over het maken en wijzigen van het meer geavanceerde [anti-phishingbeleid](configure-atp-anti-phishing-policies.md)in Microsoft Office 365 Defender voor Office 365 die beschikbaar zijn in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9094-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="b9094-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="b9094-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="b9094-115">**Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b9094-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="b9094-116">**De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="b9094-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="b9094-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b9094-118">Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="b9094-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b9094-119">Wanneer u een anti-phishingbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="b9094-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="b9094-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="b9094-121">Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b9094-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="b9094-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="b9094-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b9094-123">Zie de sectie Gebruik Exchange Online PowerShell voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="b9094-124">Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="b9094-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="b9094-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="b9094-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="b9094-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b9094-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="b9094-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="b9094-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b9094-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b9094-129">Als u de effectiviteit van anti-phishingbeveiliging wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b9094-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9094-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b9094-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b9094-131">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b9094-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b9094-132">Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="b9094-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="b9094-133">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9094-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="b9094-134">U kunt anti-phishingbeleid niet beheren in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9094-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="b9094-135">U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b9094-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b9094-136">Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="b9094-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b9094-137">Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="b9094-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="b9094-138">Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="b9094-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b9094-139">**Notes**:</span></span>

  - <span data-ttu-id="b9094-140">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9094-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b9094-141">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="b9094-142">De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="b9094-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="b9094-143"><sup>\*</sup> In het & compliancecentrum kunnen gebruikers met alleen-lezen toegang de instellingen van aangepast anti-phishingbeleid bekijken.</span><span class="sxs-lookup"><span data-stu-id="b9094-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="b9094-144">Alleen-lezen gebruikers kunnen de instellingen niet zien in het standaard anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="b9094-145">Als u anti-phishingbeleid wilt maken en wijzigen in zelfstandige EOP, moet u iets doen dat _hydratatie_ vereist voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="b9094-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="b9094-146">In het Exchange-beheercentrum (EAC) kunt u bijvoorbeeld  naar het tabblad Machtigingen gaan, een bestaande rollengroep selecteren, op pictogram Bewerken klikken en een rol verwijderen (die u uiteindelijk weer  ![ ](../../media/ITPro-EAC-EditIcon.png) toevoegt).</span><span class="sxs-lookup"><span data-stu-id="b9094-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="b9094-147">Als uw tenant nooit is gehydrateerd, krijgt u een dialoogvenster met **de naam** Organisatie bijwerken Instellingen met een voortgangsbalk die moet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="b9094-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="b9094-148">Zie de cmdlet [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in zelfstandige EOP PowerShell of in het Beveiligings- & Compliancecentrum) voor meer informatie over hydratatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="b9094-149">Zie Standaardinstellingen voor anti-phishingbeleid voor EOP voor onze aanbevolen instellingen voor [anti-phishingbeleid.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b9094-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="b9094-150">Maximaal 30 minuten toestaan dat het bijgewerkte beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="b9094-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="b9094-151">Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="b9094-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="b9094-152">Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="b9094-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="b9094-153">Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="b9094-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="b9094-154">Wanneer u een anti-phishingbeleid maakt, kunt u alleen de naam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="b9094-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="b9094-155">Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="b9094-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="b9094-156">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-157">Klik op **de pagina Anti-phishing** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="b9094-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="b9094-158">De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="b9094-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="b9094-159">Configureer **op de pagina** Naam uw beleid de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b9094-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b9094-160">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b9094-161">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b9094-162">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b9094-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b9094-163">Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="b9094-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b9094-164">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="b9094-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b9094-165">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b9094-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b9094-166">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b9094-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b9094-167">Klik **op Een voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="b9094-167">Click **Add a condition**.</span></span> <span data-ttu-id="b9094-168">Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="b9094-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b9094-169">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="b9094-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b9094-170">**De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="b9094-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b9094-171">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b9094-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="b9094-172">Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**</span><span class="sxs-lookup"><span data-stu-id="b9094-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b9094-173">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="b9094-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b9094-174">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="b9094-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b9094-175">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="b9094-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b9094-176">Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="b9094-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b9094-177">Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="b9094-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b9094-178">Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="b9094-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b9094-179">Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="b9094-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b9094-180">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="b9094-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b9094-181">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b9094-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b9094-182">Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b9094-183">U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9094-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b9094-184">Wanneer u klaar bent, klikt u op **Dit beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="b9094-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="b9094-185">Klik **op OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="b9094-186">Nadat u het anti-phishingbeleid met deze algemene beleidsinstellingen hebt gemaakt, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="b9094-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="b9094-187">Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b9094-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="b9094-188">Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="b9094-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="b9094-189">Als u er nog niet bent, opent u het Beveiligingscentrum & compliancecentrum en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-190">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9094-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="b9094-191">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b9094-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b9094-192">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="b9094-193">Als u in **een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="b9094-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="b9094-194">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="b9094-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="b9094-195">Nadat u **in** een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling, maar  u kunt in elke volgorde binnen de pagina's springen en u kunt op Opslaan op een pagina klikken (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** pictogram Annuleren of Sluiten sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="b9094-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="b9094-196">**Beleidsinstelling:** Klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het [beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="b9094-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="b9094-197">**Naam**</span><span class="sxs-lookup"><span data-stu-id="b9094-197">**Name**</span></span>
   - <span data-ttu-id="b9094-198">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="b9094-198">**Description**</span></span>
   - <span data-ttu-id="b9094-199">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="b9094-199">**Applied to**</span></span>
   - <span data-ttu-id="b9094-200">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="b9094-200">**Review your settings**</span></span>

   <span data-ttu-id="b9094-201">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="b9094-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="b9094-202">**Spoof:** Klik op **Bewerken** om spoofinformatie in of uit te schakelen, unauthenticated sender identification in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="b9094-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="b9094-203">Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie over deze instellingen.</span><span class="sxs-lookup"><span data-stu-id="b9094-203">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="b9094-204">Houd er rekening mee dat deze instellingen ook beschikbaar zijn in anti-phishingbeleid in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9094-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="b9094-205">**Filterinstellingen voor spoofing:** gebruik de instelling **Spoof intelligence inschakelen?** om spoofinformatie in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-205">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="b9094-206">De standaardwaarde is **Aan** en we raden u aan deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="b9094-206">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="b9094-207">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-207">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="b9094-208">U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-208">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b9094-209">Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="b9094-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="b9094-210">**Instellingen voor niet-nautische afzenders:** U kunt de volgende instellingen configureren:</span><span class="sxs-lookup"><span data-stu-id="b9094-210">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="b9094-211">**Unauthenticated sender question mark (?)** symbol inschakelen? : Met deze instellingen wordt het vraagteken toegevoegd aan de foto van de  afzender in het vak Van in Outlook als het bericht niet door SPF- of DKIM-controles komt en het bericht niet door DMARC of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="b9094-211">**Enable unauthenticated sender question mark (?) symbol?**: This settings adds question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="b9094-212">De standaardwaarde is **Aan**.</span><span class="sxs-lookup"><span data-stu-id="b9094-212">The default value is **On**.</span></span> <span data-ttu-id="b9094-213">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-213">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="b9094-214">**Tag 'via' inschakelen?**: met deze instelling wordt een via-tag (chris@contoso.com via fabrikam.com) toegevoegd die verschilt van het domein in de DKIM-handtekening of het **ADRES MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="b9094-214">**Enable "via" tag?**: This setting adds a via tag (chris@contoso.com via fabrikam.com) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="b9094-215">De standaardwaarde is **Aan**.</span><span class="sxs-lookup"><span data-stu-id="b9094-215">The default value is **On**.</span></span> <span data-ttu-id="b9094-216">Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-216">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="b9094-217">**Acties:** Geef de actie op voor berichten van geblokkeerde vervalste afzenders:</span><span class="sxs-lookup"><span data-stu-id="b9094-217">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="b9094-218">**Als e-mail wordt verzonden door iemand die uw** domein niet mag vervalsen:</span><span class="sxs-lookup"><span data-stu-id="b9094-218">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="b9094-219">**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b9094-219">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="b9094-220">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="b9094-220">**Quarantine the message**</span></span>

   - <span data-ttu-id="b9094-221">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="b9094-221">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="b9094-222">U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="b9094-222">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="b9094-223">U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="b9094-223">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="b9094-224">**Instellingen voor spooffilters**</span><span class="sxs-lookup"><span data-stu-id="b9094-224">**Spoof filter settings**</span></span>
       - <span data-ttu-id="b9094-225">**Instellingen voor niet-genauteerde afzender**</span><span class="sxs-lookup"><span data-stu-id="b9094-225">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="b9094-226">**Acties**</span><span class="sxs-lookup"><span data-stu-id="b9094-226">**Actions**</span></span>

   <span data-ttu-id="b9094-227">Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.</span><span class="sxs-lookup"><span data-stu-id="b9094-227">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="b9094-228">Bekijk de instellingen op **de \<Name\> pagina** Uw beleid bewerken en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="b9094-228">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="b9094-229">Gebruik het beveiligings- & compliancecentrum om het standaard anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b9094-229">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="b9094-230">Het standaard anti-phishingbeleid heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="b9094-230">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="b9094-231">Als u het standaard anti-phishingbeleid wilt wijzigen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="b9094-231">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="b9094-232">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-232">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-233">Klik op **de pagina Anti-phishing** op **Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="b9094-233">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="b9094-234">De **pagina Uw beleid bewerken Office365 AntiPhish Default** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-234">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="b9094-235">Alleen de **sectie Spoof** is beschikbaar, die identieke instellingen bevat voor wanneer u een aangepast [beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="b9094-235">Only the **Spoof** section is available, which contains identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   <span data-ttu-id="b9094-236">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="b9094-236">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="b9094-237">U kunt  de sectie Beleidsinstelling en -waarden  zien, maar er is geen koppeling Bewerken, dus u kunt de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (dit geldt voor alle geadresseerden)).</span><span class="sxs-lookup"><span data-stu-id="b9094-237">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="b9094-238">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b9094-238">You can't delete the default policy.</span></span>
   - <span data-ttu-id="b9094-239">U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="b9094-239">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="b9094-240">Controleer op **de pagina Uw beleid bewerken Office365 AntiPhish Default** uw instellingen en klik vervolgens op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="b9094-240">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="b9094-241">Aangepaste anti-phishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b9094-241">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="b9094-242">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-242">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-243">Let op de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="b9094-243">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b9094-244">Schuif de schakelknop naar  ![ Uit-schakelknop uit ](../../media/scc-toggle-off.png) om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-244">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="b9094-245">Schuif de schakelknop naar  ![ Aan-aan om ](../../media/scc-toggle-on.png) het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-245">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="b9094-246">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-246">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="b9094-247">De prioriteit instellen van aangepast anti-phishingbeleid</span><span class="sxs-lookup"><span data-stu-id="b9094-247">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="b9094-248">Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="b9094-248">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="b9094-249">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="b9094-249">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b9094-250">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="b9094-250">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b9094-251">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b9094-251">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b9094-252">Aangepaste anti-phishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="b9094-252">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b9094-253">Het standaard anti-phishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laag** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9094-253">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="b9094-254">**Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b9094-254">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="b9094-255">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="b9094-255">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b9094-256">Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het Beveiligings- & Compliancecentrum).</span><span class="sxs-lookup"><span data-stu-id="b9094-256">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="b9094-257">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="b9094-257">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="b9094-258">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-259">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9094-259">Select the policy that you want to modify.</span></span> <span data-ttu-id="b9094-260">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b9094-260">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b9094-261">Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-261">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="b9094-262">Het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b9094-262">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b9094-263">Het aangepaste anti-phishingbeleid  met de laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b9094-263">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b9094-264">Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, hebben  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b9094-264">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b9094-265">Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b9094-265">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b9094-266">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="b9094-266">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="b9094-267">Het beveiligings- & compliancecentrum gebruiken om anti-phishingbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="b9094-267">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="b9094-268">Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-268">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-269">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="b9094-269">Do one of the following steps:</span></span>

   - <span data-ttu-id="b9094-270">Selecteer een aangepast anti-phishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-270">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="b9094-271">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b9094-271">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="b9094-272">Klik **op Standaardbeleid** om het standaardbeleid voor anti-phishing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b9094-272">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="b9094-273">Het **fly-out \<name\>** Beleid bewerken wordt weergegeven, waar u de instellingen en waarden kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="b9094-273">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="b9094-274">Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b9094-274">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="b9094-275">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="b9094-276">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b9094-276">Select the policy that you want to remove.</span></span> <span data-ttu-id="b9094-277">Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b9094-277">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b9094-278">Klik in **het \<name\> flyout** Beleid bewerken dat wordt weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-278">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="b9094-279">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b9094-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="b9094-280">Gebruik Exchange Online PowerShell om anti-phishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="b9094-280">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="b9094-281">Zoals eerder beschreven, bestaat een anti-phishingbeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="b9094-281">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="b9094-282">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="b9094-282">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="b9094-283">U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="b9094-283">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="b9094-284">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="b9094-284">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b9094-285">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="b9094-285">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="b9094-286">Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="b9094-286">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="b9094-287">De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties met Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9094-287">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="b9094-288">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="b9094-288">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="b9094-289">Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="b9094-289">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b9094-290">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-290">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="b9094-291">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="b9094-291">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="b9094-292">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b9094-292">**Notes**:</span></span>

- <span data-ttu-id="b9094-293">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="b9094-293">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="b9094-294">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="b9094-294">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="b9094-295">U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="b9094-295">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="b9094-296">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="b9094-296">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="b9094-297">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="b9094-297">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="b9094-298">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum als u het beleid aan een anti-phish-regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="b9094-298">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="b9094-299">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="b9094-299">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="b9094-300">Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-300">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="b9094-301">In dit voorbeeld wordt een anti-phish-beleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="b9094-301">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="b9094-302">De beschrijving is: Het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="b9094-302">The description is: Research department policy.</span></span>
- <span data-ttu-id="b9094-303">Wijzigt de standaardactie voor spoofing in Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="b9094-303">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="b9094-304">Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-304">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="b9094-305">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="b9094-305">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="b9094-306">Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-306">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b9094-307">In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="b9094-307">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="b9094-308">De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="b9094-308">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="b9094-309">De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="b9094-309">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="b9094-310">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b9094-310">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="b9094-311">Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-311">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="b9094-312">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="b9094-312">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="b9094-313">Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="b9094-313">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b9094-314">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-314">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="b9094-315">Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="b9094-315">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="b9094-316">Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-316">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="b9094-317">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="b9094-317">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="b9094-318">Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-318">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b9094-319">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b9094-319">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="b9094-320">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="b9094-320">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="b9094-321">Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b9094-321">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="b9094-322">Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-322">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="b9094-323">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b9094-323">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="b9094-324">Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u een beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.</span><span class="sxs-lookup"><span data-stu-id="b9094-324">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="b9094-325">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9094-325">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="b9094-326">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="b9094-326">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b9094-327">Wanneer u de naam van een anti-phishingbeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="b9094-327">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="b9094-328">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-328">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b9094-329">Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-329">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="b9094-330">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="b9094-330">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="b9094-331">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="b9094-331">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b9094-332">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b9094-332">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="b9094-333">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.</span><span class="sxs-lookup"><span data-stu-id="b9094-333">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="b9094-334">Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-334">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b9094-335">Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-335">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="b9094-336">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="b9094-336">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="b9094-337">Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b9094-337">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="b9094-338">U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="b9094-338">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="b9094-339">Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-339">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="b9094-340">In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b9094-340">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b9094-341">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b9094-341">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b9094-342">Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-342">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="b9094-343">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="b9094-343">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="b9094-344">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="b9094-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b9094-345">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="b9094-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b9094-346">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b9094-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b9094-347">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="b9094-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b9094-348">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="b9094-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b9094-349">Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-349">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b9094-350">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="b9094-350">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b9094-351">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="b9094-351">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b9094-352">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="b9094-352">**Notes**:</span></span>

- <span data-ttu-id="b9094-353">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="b9094-353">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="b9094-354">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.</span><span class="sxs-lookup"><span data-stu-id="b9094-354">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="b9094-355">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b9094-355">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="b9094-356">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b9094-356">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="b9094-357">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-357">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b9094-358">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b9094-358">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b9094-359">Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-359">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="b9094-360">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b9094-360">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="b9094-361">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b9094-361">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="b9094-362">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9094-362">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="b9094-363">In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b9094-363">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b9094-364">Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="b9094-364">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b9094-365">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="b9094-365">How do you know these procedures worked?</span></span>

<span data-ttu-id="b9094-366">Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="b9094-366">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="b9094-367">Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9094-367">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="b9094-368">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="b9094-368">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b9094-369">Ga als volgt te werk om meer details weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b9094-369">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="b9094-370">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="b9094-370">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="b9094-371">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="b9094-371">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="b9094-372">Vervang Exchange Online PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="b9094-372">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```