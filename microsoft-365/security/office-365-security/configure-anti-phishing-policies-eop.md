---
title: Anti-phishings beleid configureren in EOP
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
description: Beheerders kunnen leren hoe u het anti-phishingfilter kunt maken, wijzigen en verwijderen dat beschikbaar is in organisaties met een Exchange Online-bescherming (EOP) met of zonder postvakken van Exchange Online.
ms.openlocfilehash: 69ab17263ab8c0cc03d3bc4aed6bdf39b251b9fb
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572523"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="ee6d8-103">Anti-phishings beleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="ee6d8-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ee6d8-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken is er een standaard anti-phishingfilter met een beperkt aantal anti-spoofings functies die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="ee6d8-105">Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="ee6d8-106">Beheerders kunnen het standaard anti phishingfilter-beleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="ee6d8-107">Voor een betere granulatie kunt u ook een aangepast anti-phishings beleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="ee6d8-108">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="ee6d8-109">Organisaties met Exchange Online-postvakken kunnen anti-phishings beleid in het beveiligings & nalevings centrum of in Exchange Online PowerShell configureren.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="ee6d8-110">Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van de beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="ee6d8-111">Voor informatie over het maken en aanpassen van het Geavanceerd anti-phishingfilter in Microsoft Defender voor Office 365 365, Zie [anti phishingfilter configureren in Microsoft Defender voor office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-111">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="ee6d8-112">De basisonderdelen van een anti phishingfilter zijn:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-112">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="ee6d8-113">**Het anti-virus beleid**: Hiermee geeft u de phishing-beveiliging op om in of uit te schakelen, en de acties voor het toepassen van opties.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-113">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="ee6d8-114">**De anti-phishings regel**: Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (wie het beleid van toepassing is) voor een anti-phishing beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-114">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="ee6d8-115">Het verschil tussen deze twee elementen is niet duidelijk wanneer u een anti-phishing beleid beheert in de beveiligings & nalevings centrum:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-115">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="ee6d8-116">Wanneer u een anti-Phishingfilter maakt, maakt u in feite een anti-phishings regel en het bijbehorende anti-phishings beleid op hetzelfde moment met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-116">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="ee6d8-117">Wanneer u een anti-phishingfilter wijzigt, worden de instellingen voor de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-117">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="ee6d8-118">Alle andere instellingen wijzigen het bijbehorende anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-118">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="ee6d8-119">Wanneer u een anti phishingfilter verwijdert, worden de anti-phishings regel en het bijbehorende anti-onphishings beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-119">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="ee6d8-120">In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-120">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="ee6d8-121">Zie voor meer informatie de sectie [Exchange Online PowerShell gebruiken voor het configureren van anti-phishingfilter](#use-exchange-online-powershell-to-configure-anti-phishing-policies) -secties verderop in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-121">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="ee6d8-122">Elke organisatie heeft een ingebouwd anti-phishingfilter met de naam Office365 AntiPhish standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-122">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="ee6d8-123">Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-avond regel (Recipient filters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-123">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="ee6d8-124">Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-124">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="ee6d8-125">Alle beleid dat u maakt heeft altijd een hogere prioriteit.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-125">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="ee6d8-126">Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-126">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="ee6d8-127">Voor een grotere effectiviteit van de bescherming tegen phishing is het mogelijk om een aangepast anti-phishings beleid te maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-127">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ee6d8-128">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ee6d8-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ee6d8-129">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-129">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ee6d8-130">Als u rechtstreeks naar de **anti malafide** pagina wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-130">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="ee6d8-131">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="ee6d8-132">U kunt geen anti-phishings beleid beheren in standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-132">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="ee6d8-133">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-133">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ee6d8-134">Als u een anti-phishings beleid wilt toevoegen, wijzigen of verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-134">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ee6d8-135">Voor alleen-lezen toegang tot anti phishingfilter moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-135">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="ee6d8-136">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ee6d8-137">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-137">**Notes**:</span></span>

  - <span data-ttu-id="ee6d8-138">Door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het Microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in het beveiligings & nalevings centrum _en_ machtigingen voor andere functies in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ee6d8-139">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-139">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ee6d8-140">De functiegroep **alleen weergeven voor Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-140">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="ee6d8-141"><sup>\*</sup> In het beveiligings & voor nalevings centrum kunt u met alleen-lezen toegang de instellingen van een aangepast anti-phishing beleid bekijken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-141"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="ee6d8-142">Alleen-lezen gebruikers kunnen de instellingen van het standaard anti-Phishingfilter niet zien.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-142">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="ee6d8-143">Als u een anti-phishings beleid wilt maken en wijzigen in een zelfstandige EOP, moet u iets doen waarvoor _bidons_ voor uw Tenant is vereist.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-143">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="ee6d8-144">In het Exchange-Beheercentrum gaat u bijvoorbeeld naar het tabblad **machtigingen** , selecteert u een bestaande rollen groep, klikt u op **Edit** ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) en verwijdert u een functie (die u uiteindelijk later gaat toevoegen).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-144">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="ee6d8-145">Als uw Tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **organisatie-instellingen bijwerken** met een voortgangsbalk die succesvol moet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-145">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="ee6d8-146">Als u meer wilt weten over bidons, raadpleegt u de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in een zelfstandige EOP PowerShell of in het beveiligings & nalevings centrum).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-146">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="ee6d8-147">Voor de aanbevolen instellingen voor het anti-phishings beleid raadpleegt u [EOP standaard anti phishingfilter-beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-147">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="ee6d8-148">Maximaal 30 minuten toegestaan voor het nieuwe beleid dat u wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-148">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="ee6d8-149">Zie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar anti phishingfilter in de filter pijplijn wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-149">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="ee6d8-150">Beveiligings & voor compliance gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-150">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="ee6d8-151">Als u een aangepast anti-Phishingfilter maakt in het compliance-& Beveiligingscentrum, maakt u op hetzelfde moment de anti-phishing regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-151">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="ee6d8-152">Wanneer u een anti Phishingfilter maakt, kunt u alleen de Beleidsnaam, de beschrijving en het filter voor de ontvanger opgeven waarmee wordt aangegeven voor wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-152">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="ee6d8-153">Nadat u het beleid hebt gemaakt, kunt u het beleid wijzigen, zodat u de standaardinstellingen voor anti phishing kunt wijzigen of bekijken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-153">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="ee6d8-154">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing** beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-155">Op de **anti phishing** -pagina klikt u op **maken**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-155">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="ee6d8-156">De wizard **nieuw anti-phishingfilterbeleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-156">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="ee6d8-157">Configureer de volgende instellingen op de pagina **naam van uw beleid** :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-157">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="ee6d8-158">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-158">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="ee6d8-159">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-159">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="ee6d8-160">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-160">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ee6d8-161">Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-161">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="ee6d8-162">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-162">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="ee6d8-163">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-163">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="ee6d8-164">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-164">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="ee6d8-165">Klik op **een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-165">Click **Add a condition**.</span></span> <span data-ttu-id="ee6d8-166">Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als**:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-166">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="ee6d8-167">**De ontvanger is**: geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-167">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="ee6d8-168">**De ontvanger is lid van**: Hiermee geeft u een of meer groepen op in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-168">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="ee6d8-169">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-169">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="ee6d8-170">Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-170">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="ee6d8-171">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-171">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="ee6d8-172">Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-172">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="ee6d8-173">Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-173">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="ee6d8-174">Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-174">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="ee6d8-175">Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-175">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="ee6d8-176">Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-176">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="ee6d8-177">Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-177">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="ee6d8-178">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-178">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="ee6d8-179">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-179">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ee6d8-180">Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-180">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="ee6d8-181">U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-181">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="ee6d8-182">Wanneer u klaar bent, klikt u op **dit beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-182">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="ee6d8-183">Klik op **OK** in het bevestigingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-183">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="ee6d8-184">Nadat u het anti phishingfilter met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in het volgende gedeelte om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-184">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="ee6d8-185">De beveiligings & voor compliance gebruiken om een anti-phishings beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-185">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="ee6d8-186">Gebruik de volgende procedures om een anti-phishingfilter te wijzigen: een nieuwe beleidsregels die u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-186">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="ee6d8-187">Als u dit nog niet hebt gedaan, opent u het beveiligings & nalevings centrum en gaat u naar beleid voor **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-187">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-188">Selecteer het aangepaste anti-phishingfilter dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-188">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="ee6d8-189">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-189">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee6d8-190">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-190">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="ee6d8-191">Als u in een sectie op **bewerken** klikt, krijgt u toegang tot de instellingen in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-191">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="ee6d8-192">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in een willekeurige volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-192">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="ee6d8-193">Nadat u op **bewerken** in een sectie hebt geklikt, worden de beschikbare instellingen in de wizard indeling weergegeven, maar u kunt wel binnen de pagina's in een willekeurige Volg **Cancel** orde springen **Close** , en u kunt op de pagina **Opslaan** of sluiten klikken op het pictogram voor het ![ ](../../media/scc-remove-icon.png) **bewerken van uw beleid \<name\>** (u hoeft niet te klikken op de laatste pagina van de wizard om de pagina te openen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-193">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="ee6d8-194">**Beleidsinstelling**: Klik op **bewerken** als u de instellingen wilt wijzigen die beschikbaar waren wanneer u [het beleid hebt gemaakt](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-194">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="ee6d8-195">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-195">**Name**</span></span>
   - <span data-ttu-id="ee6d8-196">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-196">**Description**</span></span>
   - <span data-ttu-id="ee6d8-197">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-197">**Applied to**</span></span>
   - <span data-ttu-id="ee6d8-198">**De instellingen bekijken**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-198">**Review your settings**</span></span>

   <span data-ttu-id="ee6d8-199">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-199">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="ee6d8-200">**Spoof**: Klik op **bewerken** als u de identiteit van spoofing wilt in-of uitschakelen, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en configureer de actie die u wilt toepassen op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-200">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="ee6d8-201">Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-201">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="ee6d8-202">Deze instellingen zijn ook beschikbaar in anti-phishing-beleid in de Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-202">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="ee6d8-203">**Instellingen voor spoofing filter**: de standaardwaarde is **ingeschakeld** en u wordt aangeraden deze in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-203">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="ee6d8-204">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-204">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="ee6d8-205">Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-205">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="ee6d8-206">U hoeft geen anti-spoofing-beveiliging uit te schakelen als uw MX-record niet verwijst naar Microsoft 365. u kunt in plaats hiervan uitgebreid filteren op connectors.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-206">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="ee6d8-207">Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-207">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="ee6d8-208">**Functie niet-geverifieerde afzender inschakelen**: de standaardwaarde is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-208">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="ee6d8-209">Verschuif de wissel **knop om deze** uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-209">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="ee6d8-210">**Acties**: de actie opgeven die moet worden uitgevoerd voor berichten die geen spoof Intelligence hebben:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-210">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="ee6d8-211">**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen, doet u het** volgende:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-211">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="ee6d8-212">**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-212">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="ee6d8-213">**Het bericht Quarantine**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-213">**Quarantine the message**</span></span>

   - <span data-ttu-id="ee6d8-214">**Controleer uw instellingen**: in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-214">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="ee6d8-215">U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-215">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="ee6d8-216">U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-216">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="ee6d8-217">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-217">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="ee6d8-218">**Niet-geverifieerde afzender functie inschakelen**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-218">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="ee6d8-219">Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-219">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="ee6d8-220">Ga op de pagina **\<Name\> beleid bewerken** naar de instellingen en klik op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-220">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="ee6d8-221">Met behulp van het nalevings centrum voor beveiliging & u het standaard anti-phishingfilter beleid wijzigen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-221">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="ee6d8-222">Het standaard anti-Phishingfilter wordt de naam Office365 AntiPhish standaard genoemd en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-222">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="ee6d8-223">Ga als volgt te werk om het standaard anti-phishingfilter te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-223">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="ee6d8-224">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing** beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-225">Klik op de pagina **anti phishing** op **standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-225">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="ee6d8-226">De standaardpagina voor het **bewerken van uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-226">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="ee6d8-227">De volgende secties zijn beschikbaar, met een identieke instelling voor [het wijzigen van een aangepast beleid](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-227">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="ee6d8-228">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-228">**Impersonation**</span></span>
   - <span data-ttu-id="ee6d8-229">**Met**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-229">**Spoof**</span></span>
   - <span data-ttu-id="ee6d8-230">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="ee6d8-230">**Advanced settings**</span></span>

   <span data-ttu-id="ee6d8-231">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-231">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="ee6d8-232">U ziet de secties en waarden van de **beleidsinstelling** , maar er is geen koppeling voor **bewerken** , zodat u de instellingen (Beleidsnaam en beschrijving, en wie het beleid van toepassing is op alle geadresseerden), niet kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-232">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="ee6d8-233">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-233">You can't delete the default policy.</span></span>
   - <span data-ttu-id="ee6d8-234">Het is niet mogelijk om de prioriteit van het standaardbeleid te wijzigen (dit wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-234">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="ee6d8-235">Controleer de instellingen op de pagina **uw beleid Office365 AntiPhish standaard** instellen en klik op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-235">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="ee6d8-236">Aangepast anti-phishings beleid in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-236">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="ee6d8-237">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing** beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-237">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-238">Let op de waarde in de kolom **status** :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-238">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="ee6d8-239">Schuif de wisselknop naar **uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-239">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="ee6d8-240">Schuif de wisselknop naar **aan om het beleid in te** schakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-240">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="ee6d8-241">U kunt het standaard anti-Phishingfilter niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-241">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="ee6d8-242">De prioriteit van een aangepast anti-phishings beleid instellen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-242">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="ee6d8-243">Standaard krijgt u een anti-phishingfilter met een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels zijn een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-243">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="ee6d8-244">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-244">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="ee6d8-245">Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-245">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="ee6d8-246">Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-246">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="ee6d8-247">Een aangepast anti-phishings beleid wordt weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="ee6d8-248">Het standaard anti-phishingfilter met de naam Office365 AntiPhish standaard heeft de waarde van een aangepaste **prioriteit en kunt** deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="ee6d8-249">**Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het anti phishingfilter wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="ee6d8-250">In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor de anti-phishing maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="ee6d8-251">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **prioriteit verhogen** of **prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **prioriteits** nummer niet rechtstreeks wijzigen in de beveiligings & compliance Center).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="ee6d8-252">Als u meerdere beleidsregels hebt, kunt u de prioriteit van een beleid alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="ee6d8-253">Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-254">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="ee6d8-255">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee6d8-256">De flyout **uw beleid \<name\> bewerken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="ee6d8-257">Het aangepaste anti-phishingfilter met de **prioriteits** waarde **0** heeft slechts de knop **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="ee6d8-258">Het aangepaste anti-phishingfilter met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is slechts de knop **prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="ee6d8-259">Als u beschikt over drie of meer aangepaste anti phishingfilter-beleidsregels, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="ee6d8-260">Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="ee6d8-261">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="ee6d8-262">Het Beveiligingscentrum voor beveiliging & gebruiken om anti phishingfilter te bekijken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="ee6d8-263">Ga in het beveiligings & compliance Center naar het beleid voor **bedreigings beheer** en ga \> **Policy** \> **tegen phishing**.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-264">Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="ee6d8-265">Selecteer een aangepast anti-phishingfilter dat u wilt bekijken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="ee6d8-266">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="ee6d8-267">Klik op **standaardbeleid** om het standaard anti-phishingfilter te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="ee6d8-268">De flyout voor het **beleid \<name\> bewerken** wordt weergegeven, waarin u de instellingen en waarden kunt weergeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="ee6d8-269">De beveiligings & gebruiken om anti phishings beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="ee6d8-270">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing** beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="ee6d8-271">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="ee6d8-272">Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="ee6d8-273">Klik in het vervolgmenu **uw beleidsregels \<name\> bewerken** dat wordt weergegeven op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="ee6d8-274">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="ee6d8-275">Een anti phishingfilter configureren met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee6d8-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="ee6d8-276">Zoals hierboven beschreven, bestaat een anti-phishings beleid en een anti-phishings regel.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-276">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="ee6d8-277">In Exchange Online PowerShell is het verschil tussen anti-malwarebeleid en anti-phishing regels zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-277">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="ee6d8-278">U een anti-phishings beleid beheert met behulp van de cmdlets **\* AntiPhishPolicy** en u beheert de anti-phishings regels met behulp van de cmdlets voor **\* AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-278">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="ee6d8-279">In PowerShell maakt u eerst het anti-phishings beleid en vervolgens maakt u een anti-phishings regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-279">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="ee6d8-280">In PowerShell wijzigt u de instellingen van het anti-phishings beleid en de anti-phishing regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-280">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="ee6d8-281">Wanneer u een anti-phishings beleid verwijdert uit PowerShell, wordt de overeenkomstige anti-phishing regel niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-281">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="ee6d8-282">De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties die gebruikmaken van Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-282">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="ee6d8-283">PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-283">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="ee6d8-284">Het maken van een anti-phishingfilter in PowerShell is een procedure die bestaat uit twee stappen:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-284">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="ee6d8-285">Maak het anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-285">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="ee6d8-286">Maak de anti-phishings regel waarmee het anti-phishings beleid wordt aangegeven waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-286">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="ee6d8-287">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-287">**Notes**:</span></span>

- <span data-ttu-id="ee6d8-288">U kunt een nieuwe anti-phishings regel maken en er een bestaande, niet-bijbehorend anti-phishings beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-288">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="ee6d8-289">Een anti-phishings regel kan niet worden gekoppeld aan meer dan een anti-phishings beleid.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-289">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="ee6d8-290">U kunt de volgende instellingen configureren voor nieuwe anti-phishings beleidsregels in PowerShell die niet beschikbaar zijn in het beveiligings & compliance Center totdat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-290">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="ee6d8-291">Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe AntiPhishRule-** cmdlet).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-291">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="ee6d8-292">De prioriteit van het beleid instellen voor het maken _Priority_ van de _\<Number\>_ **nieuwe AntiPhishRule-** cmdlet (prioriteit).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-292">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="ee6d8-293">Een nieuw anti-phishings beleid dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een anti-phishing regel toewijst.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-293">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="ee6d8-294">Stap 1: PowerShell gebruiken om een anti-phishings beleid te maken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-294">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="ee6d8-295">Voor het maken van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-295">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="ee6d8-296">In het volgende voorbeeld wordt een anti-phishings beleid met de naam onderzoek Quarantine gemaakt met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-296">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="ee6d8-297">De beschrijving luidt: afdelings beleid voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-297">The description is: Research department policy.</span></span>
- <span data-ttu-id="ee6d8-298">Wijzigt de standaardactie voor spoofing in Quarantine.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-298">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="ee6d8-299">Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-299">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="ee6d8-300">Stap 2: PowerShell gebruiken om een anti-phishings regel te maken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-300">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="ee6d8-301">Voor het maken van een anti-phishing regel gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-301">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="ee6d8-302">In dit voorbeeld wordt een anti-phishing regel genaamd onderzoek afdeling met de volgende voorwaarden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-302">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="ee6d8-303">De regel is verbonden met het anti-phishings beleid met de naam onderzoek quarantaine.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-303">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="ee6d8-304">De regel geldt voor de leden van de groep met de naam onderzoek afdeling.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-304">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="ee6d8-305">Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-305">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="ee6d8-306">Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-306">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="ee6d8-307">PowerShell gebruiken om een anti-phishings beleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-307">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="ee6d8-308">Gebruik de volgende syntaxis om de bestaande anti-phishings beleidsregels te bekijken:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-308">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ee6d8-309">In dit voorbeeld wordt een overzichtslijst met alle anti-phishing-beleidsregels en de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-309">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="ee6d8-310">In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phishings beleid met de naam leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-310">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="ee6d8-311">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-311">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="ee6d8-312">PowerShell gebruiken om anti-phishings regels te bekijken</span><span class="sxs-lookup"><span data-stu-id="ee6d8-312">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="ee6d8-313">Gebruik de volgende syntaxis om bestaande anti-phishings regels weer te geven:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-313">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="ee6d8-314">In het volgende voorbeeld wordt een overzichtslijst met alle anti-phishing regels met de opgegeven eigenschappen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-314">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="ee6d8-315">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-315">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="ee6d8-316">In het volgende voorbeeld worden alle eigenschapwaarden voor de anti-phishing-regel genaamd contoso leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-316">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="ee6d8-317">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-317">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="ee6d8-318">PowerShell gebruiken om een anti-phishings beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-318">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="ee6d8-319">Met uitzondering van de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phishings beleid in PowerShell aanpast wanneer u een beleid maakt zoals wordt beschreven in [stap 1: PowerShell gebruiken om een anti-phishings beleid te maken](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-319">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="ee6d8-320">De schakeloptie _MakeDefault_ waarmee het opgegeven beleid wordt omgezet in het standaardbeleid (voor iedereen, de **laagste** prioriteit en het niet verwijderen) is alleen beschikbaar wanneer u een anti-Echobeleid wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-320">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="ee6d8-321">U kunt niet de naam van een anti-phishings beleid wijzigen (de cmdlet **set-AntiPhishPolicy** heeft geen _naam_ parameter).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-321">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="ee6d8-322">Wanneer u de naam van een anti-phishingfilter wijzigt in de beveiligings & nalevings centrum, kunt u de naam van de anti-phishing _regel_ alleen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-322">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="ee6d8-323">Voor het wijzigen van een anti-phishings beleid gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-323">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="ee6d8-324">Zie [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-324">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="ee6d8-325">PowerShell gebruiken om anti-phishings regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-325">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="ee6d8-326">De enige instelling die niet beschikbaar is wanneer u een anti-phishing regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-326">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="ee6d8-327">Zie de volgende sectie als u bestaande anti-Phish regels wilt in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-327">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="ee6d8-328">U kunt ook dezelfde instellingen gebruiken als u een regel maakt zoals wordt beschreven in [stap 2: PowerShell gebruiken voor het maken van een anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) sectie, eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-328">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="ee6d8-329">Gebruik de volgende syntaxis om een anti-phishing regel te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-329">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="ee6d8-330">Zie [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-330">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="ee6d8-331">PowerShell gebruiken om anti-phishings regels in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-331">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="ee6d8-332">Wanneer u een anti-phishing regel in-of uitschakelt in PowerShell, schakelt u het volledige anti-phishings beleid in of uit (de anti-phishings regel en het door u toegekende anti-phishings beleid).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-332">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="ee6d8-333">U kunt het standaard anti-phishingfilter-beleid niet in-of uitschakelen (het wordt altijd toegepast op alle geadresseerden).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-333">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="ee6d8-334">U kunt een anti-phishings regel in PowerShell in-of uitschakelen met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-334">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="ee6d8-335">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-335">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee6d8-336">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-336">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee6d8-337">Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-337">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="ee6d8-338">PowerShell gebruiken om de prioriteit van anti-phishings regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-338">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="ee6d8-339">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-339">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="ee6d8-340">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-340">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="ee6d8-341">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-341">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="ee6d8-342">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-342">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="ee6d8-343">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-343">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="ee6d8-344">Als u de prioriteit wilt instellen van een anti-Phish regel in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-344">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="ee6d8-345">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-345">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="ee6d8-346">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-346">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="ee6d8-347">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-347">**Notes**:</span></span>

- <span data-ttu-id="ee6d8-348">Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-348">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="ee6d8-349">Het anti-phishings beleid heeft geen overeenkomstige anti-phishings regel, en het is altijd de **laagste** ongewijzigde prioriteitswaarde.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-349">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="ee6d8-350">PowerShell gebruiken om een anti-phishings beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-350">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="ee6d8-351">Wanneer u PowerShell gebruikt om een anti-phishings beleid te verwijderen, wordt de overeenkomstige anti-phishings regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-351">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="ee6d8-352">Gebruik de volgende syntaxis om een anti-phishings beleid te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-352">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="ee6d8-353">In dit voorbeeld wordt het anti-phishings beleid met de naam marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-353">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="ee6d8-354">Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-354">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="ee6d8-355">PowerShell gebruiken om anti-phishings regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ee6d8-355">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="ee6d8-356">Als u PowerShell gebruikt om een anti-phishing regel te verwijderen, wordt het bijbehorende anti-phishings beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-356">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="ee6d8-357">Gebruik de volgende syntaxis om een anti-phishings regel te verwijderen in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-357">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="ee6d8-358">In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-358">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="ee6d8-359">Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-359">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ee6d8-360">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="ee6d8-360">How do you know these procedures worked?</span></span>

<span data-ttu-id="ee6d8-361">Voer een van de volgende stappen uit om te controleren of u een anti-phishingfilter-beleid hebt geconfigureerd in Microsoft Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-361">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="ee6d8-362">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing** beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-362">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="ee6d8-363">Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** .</span><span class="sxs-lookup"><span data-stu-id="ee6d8-363">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="ee6d8-364">Ga op een van de volgende manieren te werk om meer informatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-364">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="ee6d8-365">Selecteer een beleid in de lijst en Bekijk de details in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-365">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="ee6d8-366">Klik op **standaardbeleid** en Bekijk de details in het vervolgmenu.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-366">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="ee6d8-367">In Exchange Online PowerShell vervangt u de \<Name\> naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="ee6d8-367">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
