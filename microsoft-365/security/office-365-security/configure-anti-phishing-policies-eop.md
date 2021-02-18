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
description: Beheerders kunnen informatie krijgen over het maken, wijzigen en verwijderen van het anti-phishingbeleid dat beschikbaar is in Exchange Online Protection-organisaties (EOP) met of zonder postvakken van Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287911"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="d1a42-103">Antiphishingbeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="d1a42-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d1a42-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d1a42-104">**Applies to**</span></span>
- [<span data-ttu-id="d1a42-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d1a42-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="d1a42-106">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal functies voor anti-spoofing bevat die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1a42-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="d1a42-107">Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="d1a42-108">Beheerders kunnen het standaard anti-phishingbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="d1a42-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="d1a42-109">Voor een grotere granulatie kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="d1a42-110">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="d1a42-111">Organisaties met Exchange Online-postvakken kunnen anti-phishingbeleid configureren in het beveiligings- & compliancecentrum of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1a42-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="d1a42-112">Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d1a42-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="d1a42-113">Zie Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie over het maken en wijzigen van het geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365 dat beschikbaar is in Defender voor [Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d1a42-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="d1a42-114">De basiselementen van een anti-phishingbeleid zijn:</span><span class="sxs-lookup"><span data-stu-id="d1a42-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="d1a42-115">**Het anti-phish-beleid:** geeft aan welke phishingbeveiliging moet worden ingeschakeld of uitgeschakeld, en wat er moet worden ondernomen om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="d1a42-116">**De anti-phish-regel:** geeft de prioriteit- en ontvangerfilters (op wie het beleid van toepassing is) voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="d1a42-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="d1a42-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d1a42-118">Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="d1a42-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="d1a42-119">Wanneer u een anti-phishingbeleid wijzigt, worden instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en filters voor geadresseerden gewijzigd in de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="d1a42-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="d1a42-121">Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="d1a42-122">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="d1a42-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="d1a42-123">Zie de sectie Exchange Online PowerShell gebruiken voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="d1a42-124">Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="d1a42-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="d1a42-125">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook als er geen anti-phish-regel (geadresseerdenfilters) aan het beleid is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d1a42-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="d1a42-126">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="d1a42-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="d1a42-127">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="d1a42-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="d1a42-128">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="d1a42-129">U kunt de effectiviteit van de beveiliging tegen phishing vergroten door een aangepast anti-phishingbeleid te maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d1a42-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d1a42-130">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d1a42-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d1a42-131">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d1a42-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d1a42-132">Als u rechtstreeks naar de **anti-phishing-pagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="d1a42-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d1a42-133">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1a42-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="d1a42-134">U kunt geen anti-phishingbeleid beheren in zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1a42-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="d1a42-135">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="d1a42-135">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d1a42-136">Als u anti-phishingbeleid wilt toevoegen, wijzigen **en** verwijderen,  moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="d1a42-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="d1a42-137">Voor alleen-lezen toegang tot anti-phishingbeleid moet u  lid zijn van de rollengroepen Globale lezer of  <sup>\*</sup> Beveiligingslezer.</span><span class="sxs-lookup"><span data-stu-id="d1a42-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="d1a42-138">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-138">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="d1a42-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d1a42-139">**Notes**:</span></span>

  - <span data-ttu-id="d1a42-140">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1a42-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d1a42-141">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="d1a42-142">De **rollengroep Organisatiebeheer alleen-weergeven** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de <sup>\*</sup> functie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-142">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="d1a42-143"><sup>\*</sup> In het & Compliancecentrum kunnen gebruikers met alleen-lezen-toegang de instellingen van aangepaste anti-phishingbeleidsregels bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="d1a42-144">Alleen-lezen gebruikers kunnen de instellingen in het standaard anti-phishingbeleid niet zien.</span><span class="sxs-lookup"><span data-stu-id="d1a42-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="d1a42-145">Als u anti-phishingbeleid wilt maken en wijzigen in de zelfstandige EOP, moet u iets doen wat voor uw tenant _vereist_ is.</span><span class="sxs-lookup"><span data-stu-id="d1a42-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="d1a42-146">In het Exchange-beheercentrum kunt u bijvoorbeeld naar  het tabblad Machtigingen gaan, een  bestaande rollengroep selecteren, op het pictogram Bewerken klikken en een rol verwijderen (die u uiteindelijk weer ![ toevoegt). ](../../media/ITPro-EAC-EditIcon.png)</span><span class="sxs-lookup"><span data-stu-id="d1a42-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="d1a42-147">Als uw tenant nog nooit gesaneerd  is, krijgt u een dialoogvenster met de naam Organisatie-instellingen bijwerken met een voortgangsbalk die zou moeten worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="d1a42-148">Zie de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in zelfstandige EOP PowerShell of in het beveiligings- & Compliancecentrum) voor meer informatie over bez.</span><span class="sxs-lookup"><span data-stu-id="d1a42-148">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="d1a42-149">Zie de EOP-standaardinstellingen voor anti-phishingbeleid voor de aanbevolen instellingen [voor anti-phishingbeleid.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="d1a42-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="d1a42-150">Het kan 30 minuten duren voordat het bijgewerkte beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="d1a42-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="d1a42-151">Zie Volgorde en prioriteit van e-mailbeveiliging voor informatie over waar anti-phishingbeleid wordt toegepast in de [filterpijplijn.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="d1a42-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="d1a42-152">Het beveiligings- & voor het maken van anti-phishingbeleidsregels</span><span class="sxs-lookup"><span data-stu-id="d1a42-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="d1a42-153">Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & Compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid op hetzelfde moment met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d1a42-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="d1a42-154">Wanneer u een anti-phishingbeleid maakt, kunt u alleen de beleidsnaam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1a42-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="d1a42-155">Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="d1a42-156">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-157">Klik op **de anti-phishing-pagina** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="d1a42-158">De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend.</span><span class="sxs-lookup"><span data-stu-id="d1a42-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="d1a42-159">Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:</span><span class="sxs-lookup"><span data-stu-id="d1a42-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="d1a42-160">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="d1a42-161">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="d1a42-162">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d1a42-163">Zoek op **de** pagina Toegepast op die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1a42-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="d1a42-164">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="d1a42-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="d1a42-165">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="d1a42-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="d1a42-166">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="d1a42-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="d1a42-167">Klik **op Voorwaarde toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-167">Click **Add a condition**.</span></span> <span data-ttu-id="d1a42-168">Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**</span><span class="sxs-lookup"><span data-stu-id="d1a42-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="d1a42-169">**De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="d1a42-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="d1a42-170">**De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="d1a42-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="d1a42-171">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="d1a42-172">Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.</span><span class="sxs-lookup"><span data-stu-id="d1a42-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="d1a42-173">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="d1a42-174">Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.</span><span class="sxs-lookup"><span data-stu-id="d1a42-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="d1a42-175">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="d1a42-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="d1a42-176">Als u afzonderlijke items wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.</span><span class="sxs-lookup"><span data-stu-id="d1a42-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="d1a42-177">Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="d1a42-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="d1a42-178">Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="d1a42-179">Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="d1a42-180">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="d1a42-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="d1a42-181">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d1a42-182">Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="d1a42-183">U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="d1a42-184">Klik op Dit beleid maken **wanneer u klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="d1a42-185">Klik **op OK** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="d1a42-186">Nadat u het anti-phishingbeleid met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="d1a42-187">Gebruik het beveiligings- & om anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1a42-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="d1a42-188">Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaand beleid dat u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="d1a42-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="d1a42-189">Als u er nog niet bent, opent u het beveiligingscentrum & compliancecentrum en gaat u **naar** Het beleid voor bedreigingsbeheer \>  \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-190">Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="d1a42-191">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1a42-192">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="d1a42-193">Als u **in een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="d1a42-194">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="d1a42-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="d1a42-195">Nadat u in een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling,  maar  u kunt in elke gewenste volgorde binnen de pagina's springen en u kunt klikken op Opslaan op een pagina (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** het pictogram Annuleren of Sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om deze op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="d1a42-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="d1a42-196">**Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het](#use-the-security--compliance-center-to-create-anti-phishing-policies) beleid in de vorige sectie maakte:</span><span class="sxs-lookup"><span data-stu-id="d1a42-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="d1a42-197">**Naam**</span><span class="sxs-lookup"><span data-stu-id="d1a42-197">**Name**</span></span>
   - <span data-ttu-id="d1a42-198">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="d1a42-198">**Description**</span></span>
   - <span data-ttu-id="d1a42-199">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="d1a42-199">**Applied to**</span></span>
   - <span data-ttu-id="d1a42-200">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="d1a42-200">**Review your settings**</span></span>

   <span data-ttu-id="d1a42-201">Wanneer u klaar bent, klikt u op **een pagina** op Opslaan.</span><span class="sxs-lookup"><span data-stu-id="d1a42-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="d1a42-202">**Spoof:**  klik op Bewerken om spoof intelligence in of uit te schakelen, identificatie van afzenders met niet-geauteerde afzender in Outlook in of uit te schakelen en de actie zo te configureren dat deze van toepassing is op berichten van geblokkeerde afzenders met spoofing.</span><span class="sxs-lookup"><span data-stu-id="d1a42-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="d1a42-203">Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="d1a42-204">Dezelfde instellingen zijn ook beschikbaar in anti-phishingbeleid in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1a42-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="d1a42-205">**Instellingen voor adresvervalsingsfilters:** de standaardwaarde is **Aan** en het is raadzaam deze ingeschakeld te laten.</span><span class="sxs-lookup"><span data-stu-id="d1a42-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="d1a42-206">Zet de schakelaar op Uit om deze uit **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="d1a42-207">Zie Spoof Intelligence configureren in EOP voor [meer informatie.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="d1a42-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="d1a42-208">U hoeft beveiliging tegen adresvervalsing niet uit te schakelen als uw MX-record niet naar Microsoft 365 betekent. hebt u in plaats daarvan Enhanced Filtering for Connectors ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1a42-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="d1a42-209">Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="d1a42-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="d1a42-210">**Functie Niet-geauteerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="d1a42-211">Zet de schakelaar op Uit om deze uit **te schakelen.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="d1a42-212">**Acties:** geef de actie op die moet worden ondernomen op berichten waarin spoof intelligence mislukt:</span><span class="sxs-lookup"><span data-stu-id="d1a42-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="d1a42-213">**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen:**</span><span class="sxs-lookup"><span data-stu-id="d1a42-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="d1a42-214">**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="d1a42-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="d1a42-215">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="d1a42-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="d1a42-216">**Controleer de instellingen:** in plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="d1a42-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="d1a42-217">U kunt in **elke sectie op** Bewerken klikken om terug te gaan naar de relevante pagina.</span><span class="sxs-lookup"><span data-stu-id="d1a42-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="d1a42-218">U kunt de volgende instellingen rechtstreeks **op** deze pagina **in-** of uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="d1a42-219">**Beveiliging tegen antispoofing inschakelen**</span><span class="sxs-lookup"><span data-stu-id="d1a42-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="d1a42-220">**Functie Niet-geauteerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="d1a42-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="d1a42-221">Wanneer u klaar bent, klikt u op **een pagina** op Opslaan.</span><span class="sxs-lookup"><span data-stu-id="d1a42-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="d1a42-222">Ga terug naar **de pagina Uw beleid bewerken, \<Name\>** controleer de instellingen en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="d1a42-223">Het beveiligings- & om het standaard anti-phishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1a42-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="d1a42-224">Het standaardbeleid tegen phishing heet Office 365 Antiphish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="d1a42-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="d1a42-225">Ga als volgt te werk om het standaardbeleid tegen phishing te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="d1a42-226">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-227">Klik op **de pagina Anti-phishing** op **Standaardbeleid.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="d1a42-228">De **pagina Uw beleid bewerken in Office 365 Antiphish Default** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="d1a42-229">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="d1a42-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="d1a42-230">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="d1a42-230">**Impersonation**</span></span>
   - <span data-ttu-id="d1a42-231">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="d1a42-231">**Spoof**</span></span>
   - <span data-ttu-id="d1a42-232">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="d1a42-232">**Advanced settings**</span></span>

   <span data-ttu-id="d1a42-233">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="d1a42-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="d1a42-234">U kunt  de sectie en waarden van de  beleidsinstelling zien, maar er is geen koppeling Bewerken. U kunt dus de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is) niet wijzigen (dit geldt voor alle geadresseerden)).</span><span class="sxs-lookup"><span data-stu-id="d1a42-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="d1a42-235">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="d1a42-236">U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="d1a42-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="d1a42-237">Controleer de instellingen op de pagina Uw beleid bewerken in **Office 365 Antiphish Default** en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="d1a42-238">Aangepaste anti-phishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="d1a42-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="d1a42-239">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-240">U ziet de waarde in de **kolom Status:**</span><span class="sxs-lookup"><span data-stu-id="d1a42-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="d1a42-241">Schuif de schakelknop naar **Uit om** het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="d1a42-242">Schuif de schakelknop naar **Aan om** het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="d1a42-243">U kunt het standaard anti-phishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="d1a42-244">De prioriteit van aangepast anti-phishingbeleid instellen</span><span class="sxs-lookup"><span data-stu-id="d1a42-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="d1a42-245">Anti-phishingbeleidsregels krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="d1a42-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="d1a42-246">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="d1a42-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="d1a42-247">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="d1a42-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="d1a42-248">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="d1a42-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="d1a42-249">Aangepaste anti-phishing-beleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0).</span><span class="sxs-lookup"><span data-stu-id="d1a42-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="d1a42-250">Het standaard antiphish-beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteit **Laagste** en u kunt deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="d1a42-251">**Opmerking:** in het & compliancecentrum kunt u de prioriteit van het anti-phishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d1a42-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="d1a42-252">In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die de prioriteit van bestaande regels kan beïnvloeden).</span><span class="sxs-lookup"><span data-stu-id="d1a42-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="d1a42-253">Als u de prioriteit van  een beleid wilt wijzigen, klikt u **in** de eigenschappen  van het beleid op Hogere prioriteit of Prioriteit verlagen (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het beveiligings- & compliancecentrum).</span><span class="sxs-lookup"><span data-stu-id="d1a42-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="d1a42-254">Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="d1a42-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="d1a42-255">Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERbeleid ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-256">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="d1a42-257">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1a42-258">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="d1a42-259">Voor het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** is alleen de **knop** Prioriteit verlagen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1a42-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="d1a42-260">Voor het aangepaste anti-phishingbeleid met de **laagste** prioriteitswaarde  (bijvoorbeeld **3)** is alleen de knop Prioriteit verhogen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1a42-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="d1a42-261">Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, zijn  voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Prioriteit **verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d1a42-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="d1a42-262">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="d1a42-263">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d1a42-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="d1a42-264">Het beveiligings- & compliancecentrum gebruiken om anti-phishingbeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="d1a42-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="d1a42-265">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-266">Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d1a42-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="d1a42-267">Selecteer een aangepast anti-phishingbeleid dat u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="d1a42-268">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="d1a42-269">Klik **op Standaardbeleid** om het standaardbeleid tegen phishing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="d1a42-270">De **flyout \<name\> Uw beleid** bewerken wordt weergegeven, waarin u de instellingen en waarden kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="d1a42-271">Het beveiligings- &-compliancecentrum gebruiken om anti-phishingbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1a42-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="d1a42-272">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="d1a42-273">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="d1a42-274">Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.</span><span class="sxs-lookup"><span data-stu-id="d1a42-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="d1a42-275">Klik in **de \<name\>** flyout Uw beleid bewerken die wordt weergegeven op Beleid verwijderen en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="d1a42-276">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="d1a42-277">Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="d1a42-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="d1a42-278">Zoals eerder is beschreven, bestaat een anti-phishingbeleid uit een anti-phish-beleid en een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="d1a42-279">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="d1a42-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="d1a42-280">U beheert anti-phish-beleid met behulp van de **\* cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="d1a42-281">In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die bepaalt op welke beleidsregel de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1a42-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="d1a42-282">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="d1a42-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="d1a42-283">Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="d1a42-284">De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties die Exchange Online Protection PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="d1a42-285">PowerShell gebruiken om anti-phishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="d1a42-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="d1a42-286">Het maken van een anti-phishingbeleid in PowerShell bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="d1a42-287">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="d1a42-288">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="d1a42-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="d1a42-289">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d1a42-289">**Notes**:</span></span>

- <span data-ttu-id="d1a42-290">U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="d1a42-291">Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="d1a42-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="d1a42-292">U kunt de volgende instellingen configureren voor nieuw anti-phish-beleid in PowerShell die pas beschikbaar zijn in het beveiligings- &-compliancecentrum nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="d1a42-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="d1a42-293">Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="d1a42-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="d1a42-294">De prioriteit van het beleid instellen tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="d1a42-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="d1a42-295">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het compliancecentrum voor beveiligings- & wanneer u het beleid toewijst aan een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="d1a42-296">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="d1a42-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="d1a42-297">Gebruik deze syntaxis om een anti-phish-beleid te maken:</span><span class="sxs-lookup"><span data-stu-id="d1a42-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="d1a42-298">In dit voorbeeld wordt een anti-phish-beleid gemaakt met de naam Research Quarantine met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="d1a42-299">De beschrijving is: het beleid van de onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="d1a42-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="d1a42-300">Wijzigt de standaardactie voor spoofing in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d1a42-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="d1a42-301">Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="d1a42-302">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="d1a42-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="d1a42-303">Gebruik de volgende syntaxis om een anti-phish-regel te maken:</span><span class="sxs-lookup"><span data-stu-id="d1a42-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="d1a42-304">In dit voorbeeld wordt een anti-phish-regel gemaakt genaamd Onderzoeksafdeling met de volgende voorwaarden:</span><span class="sxs-lookup"><span data-stu-id="d1a42-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="d1a42-305">De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="d1a42-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="d1a42-306">De regel is van toepassing op leden van de groep genaamd Onderzoeksafdeling.</span><span class="sxs-lookup"><span data-stu-id="d1a42-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="d1a42-307">Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d1a42-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="d1a42-308">Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-308">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="d1a42-309">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="d1a42-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="d1a42-310">Gebruik de volgende syntaxis om bestaand anti-phish-beleid te bekijken:</span><span class="sxs-lookup"><span data-stu-id="d1a42-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d1a42-311">In dit voorbeeld wordt een overzichtslijst van alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="d1a42-312">In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="d1a42-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="d1a42-313">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="d1a42-314">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="d1a42-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="d1a42-315">Gebruik de volgende syntaxis als u bestaande anti-phish-regels wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="d1a42-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="d1a42-316">In dit voorbeeld wordt een overzichtslijst van alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d1a42-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="d1a42-317">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="d1a42-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="d1a42-318">In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Leidinggevenden als retourneert.</span><span class="sxs-lookup"><span data-stu-id="d1a42-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="d1a42-319">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="d1a42-320">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1a42-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="d1a42-321">Met andere opties dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u een beleid maakt zoals wordt beschreven in stap 1: PowerShell gebruiken om een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="d1a42-322">De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (voor iedereen geldt, altijd de laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1a42-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="d1a42-323">U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._</span><span class="sxs-lookup"><span data-stu-id="d1a42-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="d1a42-324">Wanneer u de naam van een anti-phishingbeleid wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="d1a42-325">Gebruik de volgende syntaxis om een anti-phish-beleid te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="d1a42-326">Zie [Set-AntiPhishPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="d1a42-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="d1a42-327">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="d1a42-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="d1a42-328">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="d1a42-329">Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="d1a42-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="d1a42-330">Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap 2: PowerShell gebruiken om een sectie met [anti-phish-regels](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="d1a42-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="d1a42-331">Gebruik de volgende syntaxis om een anti-phish-regel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="d1a42-332">Zie [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="d1a42-333">PowerShell gebruiken om anti-phish-regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="d1a42-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="d1a42-334">Door een anti-phish-regel in PowerShell in of uit te schakelen, schakelt u het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in of uit.</span><span class="sxs-lookup"><span data-stu-id="d1a42-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="d1a42-335">U kunt het standaardbeleid tegen phishing niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="d1a42-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="d1a42-336">Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell in of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="d1a42-337">In dit voorbeeld wordt de anti-phish-regel met de naam Marketingafdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1a42-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1a42-338">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d1a42-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1a42-339">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="d1a42-340">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="d1a42-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="d1a42-341">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="d1a42-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="d1a42-342">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="d1a42-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="d1a42-343">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d1a42-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="d1a42-344">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="d1a42-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="d1a42-345">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="d1a42-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="d1a42-346">Gebruik de volgende syntaxis om de prioriteit van een anti-phish-regel in PowerShell in te stellen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="d1a42-347">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="d1a42-347">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="d1a42-348">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="d1a42-348">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="d1a42-349">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="d1a42-349">**Notes**:</span></span>

- <span data-ttu-id="d1a42-350">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="d1a42-351">Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare prioriteit **Laagste.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="d1a42-352">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1a42-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="d1a42-353">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="d1a42-354">Gebruik de volgende syntaxis om een anti-phish-beleid in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="d1a42-355">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="d1a42-356">Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="d1a42-357">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="d1a42-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="d1a42-358">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="d1a42-359">Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="d1a42-360">In dit voorbeeld wordt de anti-phish-regel, genaamd Marketingafdeling, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d1a42-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="d1a42-361">Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d1a42-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d1a42-362">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="d1a42-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="d1a42-363">Ga op een van de volgende stappen te werk om te controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="d1a42-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="d1a42-364">Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="d1a42-365">Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="d1a42-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="d1a42-366">Als u meer details wilt weergeven, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="d1a42-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="d1a42-367">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="d1a42-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="d1a42-368">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="d1a42-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="d1a42-369">Vervang in Exchange Online PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="d1a42-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
