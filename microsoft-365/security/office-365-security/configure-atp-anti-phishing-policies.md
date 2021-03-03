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
description: Beheerders kunnen informatie krijgen over het maken, wijzigen en verwijderen van het geavanceerde anti-phishingbeleid dat beschikbaar is in organisaties met Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d75455df972e9db0ef1cf4bbeba9f3b78b11002b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406196"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-103">Anti-phishingbeleid configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8f3c2-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-104">**Applies to**</span></span>
- [<span data-ttu-id="8f3c2-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8f3c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f3c2-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8f3c2-107">Anti-phishingbeleid in Microsoft Defender voor [Office 365](office-365-atp.md) kan uw organisatie helpen beschermen tegen kwaadaardige imitatie-phishing-aanvallen en andere soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="8f3c2-108">Zie [Anti-phishingbeveiliging](anti-phishing-protection.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in Exchange Online Protection (EOP) en anti-phishingbeleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="8f3c2-109">Beheerders kunnen het standaard anti-phishingbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="8f3c2-110">Voor een grotere granulatie kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="8f3c2-111">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="8f3c2-112">U kunt anti-phishingbeleid configureren in het & compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="8f3c2-113">Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor informatie over het configureren van de meer beperkte beleidsregels voor anti-phishing die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen organisaties zonder Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="8f3c2-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="8f3c2-115">**Het anti-phish-beleid:** geeft aan welke phishingbeveiliging moet worden ingeschakeld of uitgeschakeld, en wat er moet worden ondernomen om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="8f3c2-116">**De anti-phish-regel:** geeft de prioriteit- en ontvangerfilters (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="8f3c2-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="8f3c2-118">Wanneer u een beleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="8f3c2-119">Wanneer u een beleid wijzigt, worden de anti-phish-regel gewijzigd door instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en adressenfilters.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="8f3c2-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="8f3c2-121">Wanneer u een beleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="8f3c2-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="8f3c2-123">Zie de sectie Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren in de sectie Microsoft Defender voor [Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="8f3c2-124">Elke Organisatie van Microsoft Defender voor Office 365 heeft een ingebouwd antiphish-beleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="8f3c2-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook als er geen anti-phish-regel (geadresseerdenfilters) aan het beleid is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="8f3c2-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="8f3c2-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="8f3c2-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="8f3c2-129">Om de effectiviteit van anti-phishingbeveiliging in Microsoft Defender voor Office 365 te vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8f3c2-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8f3c2-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8f3c2-131">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8f3c2-132">Als u rechtstreeks naar de **ANTI-phishing-pagina van ATP** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="8f3c2-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="8f3c2-133">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="8f3c2-134">U moet machtigingen toegewezen krijgen in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8f3c2-135">Als u anti-phishingbeleid wilt toevoegen, wijzigen **en** verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8f3c2-136">Voor alleen-lezen toegang tot anti-phishingbeleid moet u  lid zijn van de rollengroepen Globale lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="8f3c2-137">Zie Machtigingen [in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-137">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8f3c2-138">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-138">**Notes**:</span></span>

  - <span data-ttu-id="8f3c2-139">Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol  in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8f3c2-140">Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="8f3c2-141">De **rollengroep Organisatiebeheer alleen-weergeven** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="8f3c2-142"><sup>\*</sup> In het & Compliancecentrum kunnen gebruikers met alleen-lezen-toegang de instellingen van aangepaste anti-phishingbeleidsregels bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="8f3c2-143">Alleen-lezen gebruikers kunnen de instellingen in het standaard anti-phishingbeleid niet zien.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="8f3c2-144">Voor onze aanbevolen instellingen voor anti-phishingbeleid in Microsoft Defender voor Office 365, zie [Anti-phishingbeleid in Defender voor Office 365-instellingen.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="8f3c2-145">Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="8f3c2-146">Zie Volgorde en prioriteit van e-mailbeveiliging voor informatie over waar anti-phishingbeleid wordt toegepast in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-147">Het beveiligings- & compliancecentrum gebruiken om anti-phishingbeleid te maken in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8f3c2-148">Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & Compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid op hetzelfde moment met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="8f3c2-149">Wanneer u een anti-phishingbeleid maakt, kunt u alleen de beleidsnaam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="8f3c2-150">Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="8f3c2-151">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-152">Klik op **de anti-phishing-pagina** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="8f3c2-153">De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="8f3c2-154">Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="8f3c2-155">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="8f3c2-156">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="8f3c2-157">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8f3c2-158">Zoek op **de** pagina Toegepast op die wordt weergegeven naar de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="8f3c2-159">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="8f3c2-160">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8f3c2-161">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="8f3c2-162">Klik **op Voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-162">Click **Add a condition**.</span></span> <span data-ttu-id="8f3c2-163">Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="8f3c2-164">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="8f3c2-165">**De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="8f3c2-166">**Het domein van de** ontvanger is: Geeft geadresseerden op in een of meer geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="8f3c2-167">Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="8f3c2-168">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="8f3c2-169">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="8f3c2-170">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="8f3c2-171">Als u afzonderlijke items wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="8f3c2-172">Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="8f3c2-173">Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="8f3c2-174">Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="8f3c2-175">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="8f3c2-176">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8f3c2-177">Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="8f3c2-178">U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="8f3c2-179">Klik op Dit beleid maken **wanneer u klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="8f3c2-180">Klik **op OK** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="8f3c2-181">Nadat u het anti-phishingbeleid met deze algemene instellingen hebt gemaakt, volgt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-182">Gebruik het beveiligingscentrum & anti-phishingbeleid te wijzigen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8f3c2-183">Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaand beleid dat u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="8f3c2-184">Als u er nog niet bent, opent u het beveiligings- & compliancecentrum en gaat u naar ATP voor bedreigingsbeheer  \>  \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-185">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="8f3c2-186">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="8f3c2-187">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="8f3c2-188">Als u **in een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="8f3c2-189">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="8f3c2-190">Nadat u in een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling,  maar  u kunt in elke gewenste volgorde binnen de pagina's springen en u kunt klikken op Opslaan op een pagina (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** het pictogram Annuleren of Sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om deze op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="8f3c2-191">**Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) beleid in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="8f3c2-192">**Naam**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-192">**Name**</span></span>
   - <span data-ttu-id="8f3c2-193">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-193">**Description**</span></span>
   - <span data-ttu-id="8f3c2-194">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-194">**Applied to**</span></span>
   - <span data-ttu-id="8f3c2-195">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-195">**Review your settings**</span></span>

   <span data-ttu-id="8f3c2-196">Klik op een pagina op Opslaan **wanneer** u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="8f3c2-197">**Imitatie:** klik op **Bewerken om** de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="8f3c2-198">Deze instellingen zijn een voorwaarde voor het beleid voor het identificeren van vervalste afzenders (afzonderlijk of per domein) in het Van-adres van inkomende berichten.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="8f3c2-199">Zie Imitatie-instellingen [in anti-phishingbeleid in Microsoft Defender voor Office 365 voor meer informatie.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="8f3c2-200">**Gebruikers toevoegen om te beveiligen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-201">Als u deze wilt in schakelen, schuift u de schakelaar naar **Aan** en klikt u vervolgens op de **knop** Gebruiker toevoegen die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="8f3c2-202">Configureer **de volgende waarden** in de flyout Gebruiker toevoegen die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="8f3c2-203">**E-mailadres:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-203">**Email address**:</span></span>

       - <span data-ttu-id="8f3c2-204">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="8f3c2-205">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="8f3c2-206">Als u een vermelding wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="8f3c2-207">**Naam:** deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="8f3c2-208">Klik op een pagina op Opslaan **wanneer** u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="8f3c2-209">Als u een bestaande vermelding wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="8f3c2-210">In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers (e-mailadressen van afzenders) opgeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="8f3c2-211">U kunt dezelfde beveiligde gebruiker niet opgeven in meerdere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="8f3c2-212">Beveiliging tegen gebruikers imitatie werkt niet als de afzender en ontvanger eerder via e-mail hebben gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="8f3c2-213">Als de afzender en geadresseerde nooit per e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="8f3c2-214">**Domeinen toevoegen om te beveiligen:** Configureer een of beide van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="8f3c2-215">**Neem automatisch de domeinen op die ik bezit:** de standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-216">Zet de schakelaar op Aan om deze in **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="8f3c2-217">**Aangepaste domeinen opnemen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-218">Als u deze wilt in schakelen, zet  u de schakelaar aan en typt u in het vak Domeinen toevoegen de domeinnaam (bijvoorbeeld contoso.com), drukt u op Enter en herhaalt u de stappen indien nodig.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8f3c2-219">U kunt maximaal 50 domeinen in alle anti-phishingbeleidsregels hebben.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="8f3c2-220">**Acties:** klik op **Bewerken**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="8f3c2-221">**Als e-mail** wordt verzonden door een gemitmiteerde gebruiker: Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in Gebruikers toevoegen om deze te **beveiligen:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="8f3c2-222">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="8f3c2-223">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8f3c2-224">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="8f3c2-225">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="8f3c2-226">**Bezorg het bericht en voeg andere adressen toe aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8f3c2-227">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="8f3c2-228">**Als** e-mail wordt verzonden door een gemitmiteerd domein: Configureer een van de volgende acties voor berichten waarbij de vervalste afzender zich in een van de beveiligde domeinen die u hebt opgegeven **in** Domeinen toevoegen om te beveiligen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="8f3c2-229">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="8f3c2-230">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8f3c2-231">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="8f3c2-232">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="8f3c2-233">**Bezorg het bericht en voeg andere adressen toe aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8f3c2-234">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="8f3c2-235">Klik **op Veiligheidstips voor imitatie in uitschakelen** en configureer een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="8f3c2-236">**Tip voor gebruikers die zich voordoen als imiteerd:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-237">Zet de schakelaar op Aan om deze in **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="8f3c2-238">**Tip voor gemitmiteerde domeinen:** de standaardwaarde is **Uit.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-239">Zet de schakelaar op Aan om deze in **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="8f3c2-240">**Tip voor ongebruikelijke tekens tonen:** de standaardwaarde is **Uitgeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="8f3c2-241">Zet de schakelaar op Aan om deze in **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="8f3c2-242">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="8f3c2-243">**Postvakinformatie:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="8f3c2-244">**Postvakinformatie inschakelen?**: De standaardwaarde is **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="8f3c2-245">Zet de schakelaar op Uit om deze uit **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="8f3c2-246">**Beveiliging tegen imitatie op basis van postvakintelligentie inschakelen?** Deze instelling is alleen beschikbaar als **Postvakintelligentie** inschakelen is **ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="8f3c2-247">Als e-mail wordt verzonden door een gemitmiteerde gebruiker, kunt u een van de volgende acties opgeven die moeten worden ondernomen op berichten die niet werken met postvakinformatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):</span><span class="sxs-lookup"><span data-stu-id="8f3c2-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="8f3c2-248">**Geen actie toepassen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="8f3c2-249">**Bericht omleiden naar andere e-mailadressen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="8f3c2-250">**Bericht verplaatsen naar map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="8f3c2-251">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="8f3c2-252">**Bezorg het bericht en voeg andere adressen toe aan de BCC-regel**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="8f3c2-253">**Het bericht verwijderen voordat het wordt bezorgd**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="8f3c2-254">**Vertrouwde afzenders en domeinen toevoegen:** geef uitzonderingen op voor het beleid:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="8f3c2-255">**Vertrouwde afzenders:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="8f3c2-256">Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="8f3c2-257">Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="8f3c2-258">Als u een vermelding wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="8f3c2-259">**Vertrouwde domeinen:** voer de domeinnaam in (bijvoorbeeld contoso.com), druk op Enter en herhaal deze stap indien nodig.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="8f3c2-260">**Controleer de instellingen:** in plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="8f3c2-261">U kunt in **elke sectie op** Bewerken klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="8f3c2-262">U kunt de volgende instellingen rechtstreeks **op** deze pagina **in-** of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="8f3c2-263">**Beveiligde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-263">**Protected users**</span></span>
       - <span data-ttu-id="8f3c2-264">**Beveiligde domeinen** \> **Domeinen opnemen die ik bezit**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="8f3c2-265">**Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="8f3c2-266">**Postvakinformatie**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="8f3c2-267">Klik op een pagina op Opslaan **wanneer** u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="8f3c2-268">**Spoof:**  klik op Bewerken om spoof intelligence in of uit te schakelen, identificatie van afzenders met niet-geauteerde afzender in Outlook in of uit te schakelen en de actie zo te configureren dat deze van toepassing is op berichten van geblokkeerde afzenders met spoofing.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="8f3c2-269">Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="8f3c2-270">Dezelfde instellingen zijn ook beschikbaar in anti-phishingbeleid in EOP.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="8f3c2-271">**Instellingen voor adresvervalsingsfilters:** de standaardwaarde is **Aan** en het is raadzaam deze ingeschakeld te laten.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="8f3c2-272">Zet de schakelaar op Uit om deze uit **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="8f3c2-273">Zie Spoof Intelligence configureren in EOP voor [meer informatie.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="8f3c2-274">U hoeft beveiliging tegen adresvervalsing niet uit te schakelen als uw MX-record niet naar Microsoft 365 betekent. hebt u in plaats daarvan Enhanced Filtering for Connectors ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="8f3c2-275">Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="8f3c2-276">**Functie Niet-geauteerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="8f3c2-277">Zet de schakelaar op Uit om deze uit **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="8f3c2-278">**Acties:** geef de actie op die moet worden ondernomen op berichten waarin spoof intelligence mislukt:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="8f3c2-279">**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="8f3c2-280">**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="8f3c2-281">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="8f3c2-282">**Controleer de instellingen:** in plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="8f3c2-283">U kunt in **elke sectie op** Bewerken klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="8f3c2-284">U kunt de volgende instellingen rechtstreeks **op** deze pagina **in-** of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="8f3c2-285">**Beveiliging tegen antispoofing inschakelen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="8f3c2-286">**Functie Niet-geauteerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="8f3c2-287">Klik op een pagina op Opslaan **wanneer** u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="8f3c2-288">**Geavanceerde instellingen:** klik op **Bewerken om** de geavanceerde drempelwaarden voor phishing te configureren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="8f3c2-289">Zie Geavanceerde drempelwaarden voor [phishing in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="8f3c2-290">**Geavanceerde drempelwaarden voor phishing:** selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="8f3c2-291">**1 - Standaard** (dit is de standaardwaarde.)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="8f3c2-292">**2 - Aggressive**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="8f3c2-293">**3 - Meer agressief**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="8f3c2-294">**4 - Meest agressief**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="8f3c2-295">**Controleer de instellingen:** klik op **Bewerken om** terug te gaan naar de pagina met **geavanceerde phishing-drempelwaarden.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="8f3c2-296">Klik op een van de **pagina's op Opslaan** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="8f3c2-297">Ga terug naar **de pagina Uw beleid bewerken, \<Name\>** controleer de instellingen en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-298">Het beveiligings- & om het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 te wijzigen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8f3c2-299">Het standaardbeleid tegen phishing in Microsoft Defender voor Office 365 heet Office 365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="8f3c2-300">Ga als volgt te werk om het standaardbeleid tegen phishing te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="8f3c2-301">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-302">Klik op **de pagina Anti-phishing** op **Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="8f3c2-303">De **pagina Uw beleid bewerken in Office 365 Antiphish Default** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="8f3c2-304">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="8f3c2-305">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-305">**Impersonation**</span></span>
   - <span data-ttu-id="8f3c2-306">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-306">**Spoof**</span></span>
   - <span data-ttu-id="8f3c2-307">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-307">**Advanced settings**</span></span>

   <span data-ttu-id="8f3c2-308">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="8f3c2-309">U kunt  de sectie en waarden van de  beleidsinstelling zien, maar er is geen koppeling Bewerken. U kunt dus de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is) niet wijzigen (dit geldt voor alle geadresseerden)).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="8f3c2-310">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="8f3c2-311">U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="8f3c2-312">Controleer de instellingen op de pagina Uw beleid bewerken in **Office 365 Antiphish Default** en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-313">Aangepaste anti-phishingbeleidsregels in- of uitschakelen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="8f3c2-314">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-315">U ziet de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="8f3c2-316">Schuif de schakelknop naar **Uit om** het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="8f3c2-317">Schuif de schakelknop naar **Aan om** het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="8f3c2-318">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-319">De prioriteit van aangepaste anti-phishingbeleidsregels instellen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8f3c2-320">Anti-phishingbeleidsregels krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="8f3c2-321">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="8f3c2-322">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="8f3c2-323">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="8f3c2-324">Aangepaste anti-phishing-beleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="8f3c2-325">Het standaard antiphish-beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteit **Laagste** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="8f3c2-326">**Opmerking:** in het & compliancecentrum kunt u de prioriteit van het anti-phishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="8f3c2-327">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die de prioriteit van bestaande regels kan beïnvloeden).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="8f3c2-328">Als u de prioriteit van  een beleid wilt wijzigen, klikt u **in** de eigenschappen  van het beleid op Hogere prioriteit of Prioriteit verlagen (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het beveiligings- & compliancecentrum).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="8f3c2-329">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="8f3c2-330">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-331">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="8f3c2-332">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="8f3c2-333">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="8f3c2-334">Voor het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** is alleen de **knop** Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="8f3c2-335">Voor het aangepaste anti-phishingbeleid met de **laagste** prioriteitswaarde  (bijvoorbeeld **3)** is alleen de knop Prioriteit verhogen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="8f3c2-336">Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, zijn  voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Prioriteit **verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="8f3c2-337">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="8f3c2-338">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-339">Het beveiligingscentrum & om anti-phishingbeleid weer te geven in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="8f3c2-340">Ga in het & Compliancecentrum naar  \>  \> **ATP anti-phishingbeleid** voor bedreigingsbeheer.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-341">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="8f3c2-342">Selecteer een aangepast anti-phishingbeleid dat u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="8f3c2-343">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="8f3c2-344">Klik **op Standaardbeleid** om het standaardbeleid tegen phishing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="8f3c2-345">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven, waarin u de instellingen en waarden kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-346">Het beveiligings- &-compliancecentrum gebruiken om anti-phishingbeleid te verwijderen in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="8f3c2-347">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8f3c2-348">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="8f3c2-349">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="8f3c2-350">Klik in **de \<name\>** flyout Uw beleid bewerken die wordt weergegeven op Beleid verwijderen en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="8f3c2-351">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8f3c2-352">Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3c2-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8f3c2-353">Zoals eerder is beschreven, bestaat een antispambeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="8f3c2-354">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="8f3c2-355">U beheert anti-phish-beleid met behulp van de **\* cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="8f3c2-356">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die bepaalt op welke beleidsregel de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="8f3c2-357">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="8f3c2-358">Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="8f3c2-359">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="8f3c2-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="8f3c2-360">Het maken van een anti-phishingbeleid in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="8f3c2-361">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="8f3c2-362">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="8f3c2-363">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-363">**Notes**:</span></span>

- <span data-ttu-id="8f3c2-364">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="8f3c2-365">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="8f3c2-366">U kunt de volgende instellingen configureren voor nieuw anti-phish-beleid in PowerShell die pas beschikbaar zijn in het beveiligings- &-compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="8f3c2-367">Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="8f3c2-368">De prioriteit van het beleid instellen tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="8f3c2-369">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het compliancecentrum voor beveiligings- & wanneer u het beleid toewijst aan een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="8f3c2-370">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="8f3c2-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="8f3c2-371">Gebruik deze syntaxis om een anti-phish-beleid te maken:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="8f3c2-372">In dit voorbeeld wordt een anti-phish-beleid gemaakt met de naam Research Quarantine met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="8f3c2-373">Het beleid is ingeschakeld (de parameter _Enabled_ wordt niet gebruikt en de standaardwaarde `$true` is).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="8f3c2-374">De beschrijving is: het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="8f3c2-375">Schakelt organisatiedomeinenbescherming in voor alle geaccepteerde domeinen en gerichte domeinen voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="8f3c2-376">Hiermee wordt Voor eigen mfujito@fabrikam.com opgegeven als de gebruiker die moet worden beschermd tegen imitatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="8f3c2-377">Maakt postvakinformatie mogelijk.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="8f3c2-378">Schakelt beveiliging van postvakinformatie in en geeft de quarantaineactie op.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="8f3c2-379">Hiermee worden veiligheidstips mogelijk.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="8f3c2-380">Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="8f3c2-381">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="8f3c2-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="8f3c2-382">Gebruik de volgende syntaxis om een anti-phish-regel te maken:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="8f3c2-383">In dit voorbeeld wordt een anti-phish-regel gemaakt genaamd Onderzoeksafdeling met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="8f3c2-384">De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="8f3c2-385">De regel is van toepassing op leden van de groep genaamd Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="8f3c2-386">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="8f3c2-387">Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="8f3c2-388">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="8f3c2-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="8f3c2-389">Gebruik de volgende syntaxis om bestaand anti-phish-beleid te bekijken:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8f3c2-390">In dit voorbeeld wordt een overzichtslijst van alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="8f3c2-391">In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="8f3c2-392">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="8f3c2-393">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="8f3c2-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="8f3c2-394">Gebruik de volgende syntaxis als u bestaande anti-phish-regels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8f3c2-395">In dit voorbeeld wordt een overzichtslijst van alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="8f3c2-396">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="8f3c2-397">In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="8f3c2-398">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="8f3c2-399">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="8f3c2-400">Met andere opties dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt, zoals wordt beschreven in stap 1: PowerShell gebruiken om een sectie voor [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit artikel te maken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="8f3c2-401">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (voor iedereen geldt, altijd de laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="8f3c2-402">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="8f3c2-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="8f3c2-403">Wanneer u de naam van een anti-phishingbeleid wijzigt in het beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="8f3c2-404">Gebruik de volgende syntaxis om een anti-phish-beleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="8f3c2-405">Zie [Set-AntiPhishPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="8f3c2-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="8f3c2-406">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="8f3c2-407">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="8f3c2-408">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="8f3c2-409">Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="8f3c2-410">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt, zoals beschreven in stap 2: PowerShell gebruiken om een sectie met [anti-phish-regels](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="8f3c2-411">Gebruik de volgende syntaxis om een anti-phish-regel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="8f3c2-412">Zie [Set-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="8f3c2-413">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="8f3c2-414">Door een anti-phish-regel in PowerShell in of uit te schakelen, schakelt u het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in of uit.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="8f3c2-415">U kunt het standaardbeleid tegen phishing niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="8f3c2-416">Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="8f3c2-417">In dit voorbeeld wordt de anti-phish-regel met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8f3c2-418">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8f3c2-419">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="8f3c2-420">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="8f3c2-421">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="8f3c2-422">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="8f3c2-423">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="8f3c2-424">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="8f3c2-425">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="8f3c2-426">Gebruik de volgende syntaxis om de prioriteit van een anti-phish-regel in PowerShell in te stellen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="8f3c2-427">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-427">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="8f3c2-428">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="8f3c2-428">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="8f3c2-429">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-429">**Notes**:</span></span>

- <span data-ttu-id="8f3c2-430">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="8f3c2-431">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare prioriteit **Laagste.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="8f3c2-432">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="8f3c2-433">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="8f3c2-434">Gebruik de volgende syntaxis om een anti-phish-beleid in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="8f3c2-435">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="8f3c2-436">Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="8f3c2-437">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="8f3c2-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="8f3c2-438">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="8f3c2-439">Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="8f3c2-440">In dit voorbeeld wordt de anti-phish-regel, genaamd Marketingafdeling, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="8f3c2-441">Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8f3c2-442">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="8f3c2-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="8f3c2-443">Ga op een van de volgende stappen te werk om te controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="8f3c2-444">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="8f3c2-445">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="8f3c2-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="8f3c2-446">Als u meer details wilt weergeven, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="8f3c2-447">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="8f3c2-448">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="8f3c2-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="8f3c2-449">Vervang in Exchange Online PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="8f3c2-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
