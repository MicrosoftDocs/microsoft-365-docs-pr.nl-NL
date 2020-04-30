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
description: Beheerders kunnen leren hoe ze de antiphishingbeleidsregels kunnen maken, wijzigen en verwijderen die beschikbaar zijn in EOP-organisaties (Exchange Online Protection) met of zonder Exchange Online-postvakken.
ms.openlocfilehash: 770990cdd7927ebb8afa088f2d5be09c75824d59
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949269"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="9b024-103">Anti-phishingbeleid configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="9b024-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="9b024-104">Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken hebben een standaard beleid voor antiphishing.</span><span class="sxs-lookup"><span data-stu-id="9b024-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="9b024-105">Dit beleid bevat een beperkt aantal anti-spoofing functies die standaard zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9b024-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="9b024-106">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="9b024-107">Beheerders kunnen het standaard antiphishingbeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="9b024-107">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="9b024-108">Voor meer granulariteit u ook aangepaste antiphishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-108">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="9b024-109">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="9b024-110">Organisaties met Exchange Online-postvakken kunnen antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b024-110">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="9b024-111">Zelfstandige EOP-organisaties kunnen alleen gebruik maken van het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="9b024-111">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="9b024-112">Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)voor informatie over het maken en wijzigen van de meer geavanceerde ATP-antiphishingbeleidsregels die beschikbaar zijn in Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="9b024-112">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a><span data-ttu-id="9b024-113">Anti-phishingbeleid in het Security & Compliance Center vs Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b024-113">Anti-phishing policies in the Security & Compliance Center vs Exchange Online PowerShell</span></span>

<span data-ttu-id="9b024-114">De basiselementen van een anti-phishing beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="9b024-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="9b024-115">**Het anti-phish-beleid**: Hiermee geeft u de phishingbeveiligingen op om in te schakelen of uit te schakelen, en de acties om opties toe te passen.</span><span class="sxs-lookup"><span data-stu-id="9b024-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="9b024-116">**De anti-phish-regel**: Geeft de prioriteits- en ontvangerfilters (op wie het beleid van toepassing is) op voor een anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="9b024-117">Het verschil tussen deze twee elementen is niet duidelijk wanneer u antiphishingbeleid beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="9b024-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9b024-118">Wanneer u een antiphishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="9b024-118">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="9b024-119">Wanneer u een antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en wijzigen de filters voor ontvangers de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="9b024-119">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="9b024-120">Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-120">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="9b024-121">Wanneer u een antiphishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9b024-121">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="9b024-122">In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk.</span><span class="sxs-lookup"><span data-stu-id="9b024-122">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="9b024-123">U beheert anti-phish-beleid met behulp van de \*\* \*cmdlets -AntiPhishPolicy\*\* en u beheert anti-phish-regels met behulp van de \*\* \*cmdlets -AntiPhishRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="9b024-123">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="9b024-124">In PowerShell maakt u eerst het anti-phish-beleid, vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="9b024-124">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="9b024-125">In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="9b024-125">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="9b024-126">Standaard ATP anti-phishing beleid</span><span class="sxs-lookup"><span data-stu-id="9b024-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="9b024-127">Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="9b024-127">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="9b024-128">Het beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-128">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="9b024-129">Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="9b024-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="9b024-130">Elk aangepast beleid dat u maakt, heeft altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.</span><span class="sxs-lookup"><span data-stu-id="9b024-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="9b024-131">Het beleid met de naam Office365 AntiPhish Default is `True`het standaardbeleid (de eigenschap **IsDefault** heeft de waarde) en u het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b024-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="9b024-132">Om de effectiviteit van anti-phishingbescherming te vergroten, u aangepaste antiphishingbeleidsregels maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="9b024-132">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b024-133">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9b024-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b024-134">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9b024-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9b024-135">Gebruik . **Anti-phishing** <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="9b024-135">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="9b024-136">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b024-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="9b024-137">U antiphishingbeleid niet beheren in het zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b024-137">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="9b024-138">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9b024-138">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9b024-139">Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="9b024-139">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="9b024-140">Voor alleen-lezen toegang tot anti-phishingbeleid moet u lid zijn van de rolgroep **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="9b024-140">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="9b024-141">Zie [Machtigingen in het Office 365-beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="9b024-141">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="9b024-142">Om antispambeleid in standalone EOP te kunnen maken en wijzigen, moet u iets doen waarvoor _hydratatie_ voor uw tenant nodig is.</span><span class="sxs-lookup"><span data-stu-id="9b024-142">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="9b024-143">In de EAC u bijvoorbeeld naar het tabblad **Machtigingen** gaan, een bestaande rolgroep selecteren, op pictogram](../../media/ITPro-EAC-EditIcon.png)Bewerken **bewerken klikken** ![en een rol verwijderen (die u uiteindelijk weer toevoegt).</span><span class="sxs-lookup"><span data-stu-id="9b024-143">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="9b024-144">Als uw tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **Organisatie-instellingen bijwerken** met een voortgangsbalk die moet worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="9b024-144">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="9b024-145">Zie de cmdlet [Inschakelen-organisatieaanpassing](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) (die niet beschikbaar is in standalone EOP PowerShell of in het Security & Compliance Center) voor meer informatie over hydratatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-145">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="9b024-146">Zie [EOP standaard antiphishingbeleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor antiphishing.</span><span class="sxs-lookup"><span data-stu-id="9b024-146">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="9b024-147">Sta maximaal 30 minuten toe voordat het bijgewerkte beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="9b024-147">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="9b024-148">Zie [Volgorde en voorrang van e-mailbeveiliging in Office 365](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.</span><span class="sxs-lookup"><span data-stu-id="9b024-148">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="9b024-149">Gebruik het Security & Compliance Center om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="9b024-149">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="9b024-150">Als u een aangepast antiphishingbeleid maakt in het Security & Compliance Center, wordt de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9b024-150">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="9b024-151">Wanneer u een antiphishingbeleid maakt, u alleen de beleidsnaam, beschrijving en het filter voor geadresseerden opgeven dat aangeeft op wie het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="9b024-151">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="9b024-152">Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te controleren.</span><span class="sxs-lookup"><span data-stu-id="9b024-152">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="9b024-153">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-154">Klik op de **antiphishingpagina** op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="9b024-154">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="9b024-155">De wizard Een nieuwe wizard **antiphishingbeleid maken** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="9b024-155">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="9b024-156">Configureer op **de pagina Naam van uw beleid** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="9b024-156">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9b024-157">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-157">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9b024-158">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-158">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9b024-159">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-159">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9b024-160">Identificeer **op** de pagina Toegepast op die wordt weergegeven, de interne ontvangers waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="9b024-160">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9b024-161">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="9b024-161">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9b024-162">Meerdere waarden van dezelfde voorwaarde of uitzondering gebruiken OF-logica (bijv.: _\<afzender1\>_ of _\<afzender2\>_).</span><span class="sxs-lookup"><span data-stu-id="9b024-162">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9b024-163">Verschillende voorwaarden of uitzonderingen gebruiken EN-logica (bijv.: _\<geadresseerde1\>_ en _\<lid van groep 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9b024-163">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="9b024-164">Klik **op Een voorwaarde toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9b024-164">Click **Add a condition**.</span></span> <span data-ttu-id="9b024-165">Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:</span><span class="sxs-lookup"><span data-stu-id="9b024-165">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="9b024-166">**De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="9b024-166">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9b024-167">**De ontvanger is lid van**: Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="9b024-167">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9b024-168">**Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b024-168">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in Office 365.</span></span>

   <span data-ttu-id="9b024-169">Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met een **elk vak.**</span><span class="sxs-lookup"><span data-stu-id="9b024-169">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9b024-170">Klik in het vak en blader door de lijst met waarden die u wilt selecteren.</span><span class="sxs-lookup"><span data-stu-id="9b024-170">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9b024-171">Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9b024-171">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9b024-172">Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.</span><span class="sxs-lookup"><span data-stu-id="9b024-172">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9b024-173">Als u afzonderlijke vermeldingen **Remove** ![wilt](../../media/scc-remove-icon.png) verwijderen, klikt u op Pictogram Verwijderen op de waarde verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b024-173">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9b024-174">Als u de hele **Remove** ![voorwaarde](../../media/scc-remove-icon.png) wilt verwijderen, klikt u op Pictogram Verwijderen op voorwaarde.</span><span class="sxs-lookup"><span data-stu-id="9b024-174">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9b024-175">Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.</span><span class="sxs-lookup"><span data-stu-id="9b024-175">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9b024-176">Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**.</span><span class="sxs-lookup"><span data-stu-id="9b024-176">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9b024-177">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="9b024-177">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9b024-178">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-178">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9b024-179">Controleer op de pagina **Uw instellingen controleren** die wordt weergegeven, uw instellingen.</span><span class="sxs-lookup"><span data-stu-id="9b024-179">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9b024-180">U op **Bewerken** op elke instelling klikken om deze te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b024-180">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9b024-181">Klik op **Dit beleid maken**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-181">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="9b024-182">Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-182">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="9b024-183">Nadat u het antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.</span><span class="sxs-lookup"><span data-stu-id="9b024-183">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="9b024-184">Het Beveiligingscentrum & compliance center gebruiken om antiphishingbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9b024-184">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="9b024-185">Gebruik de volgende procedures om antiphishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.</span><span class="sxs-lookup"><span data-stu-id="9b024-185">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="9b024-186">Als u er nog niet bent, opent u het Beveiligingscentrum & Compliance Center en gaat u naar **Bedreigingsbeheer** \> **Anti-phishing.** **Policy** \></span><span class="sxs-lookup"><span data-stu-id="9b024-186">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-187">Selecteer het aangepaste antiphishingbeleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b024-187">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="9b024-188">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="9b024-188">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9b024-189">De flyout met de naam bewerken van \*\*uw beleid \<\> \*\* wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-189">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="9b024-190">Als u in een sectie op **Bewerken** klikt, hebt u toegang tot de instellingen in die sectie.</span><span class="sxs-lookup"><span data-stu-id="9b024-190">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="9b024-191">De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in elke volgorde selecteren en wijzigen).</span><span class="sxs-lookup"><span data-stu-id="9b024-191">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="9b024-192">Nadat u in een sectie op **Bewerken** hebt geklikt, worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in](../../media/scc-remove-icon.png) elke volgorde binnen de pagina's springen en u op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten** ![sluiten om terug te keren naar de pagina \*\*Uw beleidsnaam \<\> \*\* bewerken (u hoeft niet de laatste pagina van de wizard te bezoeken om op te slaan of te verlaten).</span><span class="sxs-lookup"><span data-stu-id="9b024-192">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="9b024-193">**Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het beleid in de vorige sectie [maakte:](#use-the-security--compliance-center-to-create-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="9b024-193">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="9b024-194">**Naam**</span><span class="sxs-lookup"><span data-stu-id="9b024-194">**Name**</span></span>
   - <span data-ttu-id="9b024-195">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="9b024-195">**Description**</span></span>
   - <span data-ttu-id="9b024-196">**Toegepast op**</span><span class="sxs-lookup"><span data-stu-id="9b024-196">**Applied to**</span></span>
   - <span data-ttu-id="9b024-197">**Uw instellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="9b024-197">**Review your settings**</span></span>

   <span data-ttu-id="9b024-198">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-198">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="9b024-199">**Spoof:** klik op **Bewerken** om spoofinformatie in- of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders.</span><span class="sxs-lookup"><span data-stu-id="9b024-199">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="9b024-200">Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-200">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="9b024-201">Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in het ANTI-phishingbeleid van ATP.</span><span class="sxs-lookup"><span data-stu-id="9b024-201">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="9b024-202">**Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten staan.</span><span class="sxs-lookup"><span data-stu-id="9b024-202">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="9b024-203">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="9b024-203">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="9b024-204">Zie [spoof-intelligentie configureren in Office 365](learn-about-spoof-intelligence.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-204">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="9b024-205">U hoeft anti-spoofingbeveiliging niet uit te schakelen als uw MX-record niet naar Office 365 wijst. u schakelt in plaats daarvan Uitgebreide filtering voor connectors in.</span><span class="sxs-lookup"><span data-stu-id="9b024-205">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="9b024-206">Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .</span><span class="sxs-lookup"><span data-stu-id="9b024-206">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="9b024-207">**Functie Niet-geverifieerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="9b024-207">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="9b024-208">Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**</span><span class="sxs-lookup"><span data-stu-id="9b024-208">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="9b024-209">**Acties:** Geef de actie op die moet worden uitgevoerd met berichten die niet in de spoofinformatie zijn geslaagd:</span><span class="sxs-lookup"><span data-stu-id="9b024-209">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="9b024-210">**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**</span><span class="sxs-lookup"><span data-stu-id="9b024-210">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="9b024-211">**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="9b024-211">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="9b024-212">**Het bericht in quarantaine plaatsen**</span><span class="sxs-lookup"><span data-stu-id="9b024-212">**Quarantine the message**</span></span>

   - <span data-ttu-id="9b024-213">**Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.</span><span class="sxs-lookup"><span data-stu-id="9b024-213">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="9b024-214">U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.</span><span class="sxs-lookup"><span data-stu-id="9b024-214">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="9b024-215">U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**</span><span class="sxs-lookup"><span data-stu-id="9b024-215">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="9b024-216">**Antispoofing-beveiliging inschakelen**</span><span class="sxs-lookup"><span data-stu-id="9b024-216">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="9b024-217">**Functie Niet-geverifieerde afzender inschakelen**</span><span class="sxs-lookup"><span data-stu-id="9b024-217">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="9b024-218">Klik op **Opslaan** op een pagina als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-218">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="9b024-219">Terug op de pagina **Uw beleidsnaam \<\> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**klikken.</span><span class="sxs-lookup"><span data-stu-id="9b024-219">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="9b024-220">Het Beveiligingscentrum & gebruiken om het standaardbeleid voor phishing te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9b024-220">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="9b024-221">Het standaard beleid voor antiphishing heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="9b024-221">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="9b024-222">Ga als volgt te werk om het standaard beleid voor antiphishing te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="9b024-222">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="9b024-223">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-223">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-224">Klik op de pagina **Anti-phishing** op **Standaardbeleid**.</span><span class="sxs-lookup"><span data-stu-id="9b024-224">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="9b024-225">De pagina **Standaardinstelling voor uw beleid Office365 AntiPhish** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-225">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="9b024-226">De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="9b024-226">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="9b024-227">**Imitatie**</span><span class="sxs-lookup"><span data-stu-id="9b024-227">**Impersonation**</span></span>
   - <span data-ttu-id="9b024-228">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="9b024-228">**Spoof**</span></span>
   - <span data-ttu-id="9b024-229">**Geavanceerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="9b024-229">**Advanced settings**</span></span>

   <span data-ttu-id="9b024-230">De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:</span><span class="sxs-lookup"><span data-stu-id="9b024-230">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="9b024-231">U de sectie **Beleidsinstelling** en waarden zien, maar er is geen **koppeling Bewerken,** dus u de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is op niet wijzigen (het is van toepassing op alle ontvangers)).</span><span class="sxs-lookup"><span data-stu-id="9b024-231">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="9b024-232">U het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b024-232">You can't delete the default policy.</span></span>
   - <span data-ttu-id="9b024-233">U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="9b024-233">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="9b024-234">Controleer op de pagina **Standaardbeleid Office365 AntiPhish bewerken** uw instellingen en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9b024-234">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="9b024-235">Aangepaste antiphishingbeleidsregels in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="9b024-235">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="9b024-236">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-236">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-237">Let op de waarde in de kolom **Status:**</span><span class="sxs-lookup"><span data-stu-id="9b024-237">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9b024-238">Schuif de schakel naar **Uit** om het beleid uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9b024-238">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="9b024-239">Schuif de schakelaar naar **Aan** om het beleid in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9b024-239">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="9b024-240">U het standaard antiphishingbeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="9b024-240">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="9b024-241">De prioriteit instellen van aangepast antiphishingbeleid</span><span class="sxs-lookup"><span data-stu-id="9b024-241">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="9b024-242">Standaard krijgen antiphishingbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwer beleid heeft een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="9b024-242">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="9b024-243">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="9b024-243">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9b024-244">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="9b024-244">No two policies can have the same priority.</span></span>

<span data-ttu-id="9b024-245">Aangepaste antiphishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="9b024-245">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="9b024-246">Het standaard antiphishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste**en u deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b024-246">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="9b024-247">**Opmerking:** In het Security & Compliance Center u de prioriteit van het antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9b024-247">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="9b024-248">In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).</span><span class="sxs-lookup"><span data-stu-id="9b024-248">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9b024-249">Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet rechtstreeks wijzigen in het Beveiligings& Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="9b024-249">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="9b024-250">Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.</span><span class="sxs-lookup"><span data-stu-id="9b024-250">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="9b024-251">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="9b024-251">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-252">Selecteer het beleid dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b024-252">Select the policy that you want to modify.</span></span> <span data-ttu-id="9b024-253">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="9b024-253">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9b024-254">De flyout met de naam bewerken van \*\*uw beleid \<\> \*\* wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-254">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="9b024-255">Het aangepaste anti-phishingbeleid met de **prioriteitswaarde** **0** heeft alleen de knop **Prioriteit verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="9b024-255">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9b024-256">Het aangepaste anti-phishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="9b024-256">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9b024-257">Als u drie of meer aangepaste antiphishingbeleidsregels hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de **prioriteitsprioriteit verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="9b024-257">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9b024-258">Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b024-258">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9b024-259">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="9b024-259">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="9b024-260">Gebruik het Beveiligingscentrum & compliance om antiphishingbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="9b024-260">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="9b024-261">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-261">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-262">Een van de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="9b024-262">Do one of the following steps:</span></span>

   - <span data-ttu-id="9b024-263">Selecteer een aangepast antiphishingbeleid dat u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-263">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="9b024-264">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="9b024-264">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="9b024-265">Klik **op Standaardbeleid** om het standaard beleid voor antiphishing weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9b024-265">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="9b024-266">De flyout met de naam bewerken van \*\*uw beleid \<\> \*\* wordt weergegeven, waar u de instellingen en waarden bekijken.</span><span class="sxs-lookup"><span data-stu-id="9b024-266">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="9b024-267">Het Beveiligingscentrum & compliance gebruiken om antiphishingbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="9b024-267">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="9b024-268">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="9b024-269">Selecteer het beleid dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b024-269">Select the policy that you want to remove.</span></span> <span data-ttu-id="9b024-270">Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="9b024-270">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="9b024-271">Klik in de flyout **van de beleidsnaam \<\> bewerken** die wordt weergegeven op Beleid **verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9b024-271">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="9b024-272">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b024-272">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="9b024-273">Exchange Online PowerShell gebruiken om antiphishingbeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="9b024-273">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="9b024-274">De volgende procedures zijn niet beschikbaar in zelfstandige EOP-organisaties.</span><span class="sxs-lookup"><span data-stu-id="9b024-274">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="9b024-275">PowerShell gebruiken om antiphishingbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="9b024-275">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="9b024-276">Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="9b024-276">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9b024-277">Maak het anti-phish-beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-277">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="9b024-278">Maak de anti-phish-regel die het anti-phish-beleid aangeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="9b024-278">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="9b024-279">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="9b024-279">**Notes**:</span></span>

- <span data-ttu-id="9b024-280">U een nieuwe anti-phish-regel maken en er een bestaand, niet-geassocieerd anti-phish-beleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="9b024-280">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="9b024-281">Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.</span><span class="sxs-lookup"><span data-stu-id="9b024-281">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="9b024-282">U de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="9b024-282">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="9b024-283">Het nieuwe beleid als uitgeschakeld maken _(ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="9b024-283">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="9b024-284">Stel de prioriteit in van het beleid tijdens het maken ( _ \<Prioriteitsnummer\>_) op de cmdlet **Nieuw-AntiPhishRule.** _Priority_</span><span class="sxs-lookup"><span data-stu-id="9b024-284">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="9b024-285">Een nieuw anti-phish-beleid dat u in PowerShell maakt, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="9b024-285">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="9b024-286">Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken</span><span class="sxs-lookup"><span data-stu-id="9b024-286">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="9b024-287">Als u een anti-phish-beleid wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-287">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="9b024-288">In dit voorbeeld wordt anti-phish-beleid met de naam Research Quarantine met de volgende instellingen gemaakt:</span><span class="sxs-lookup"><span data-stu-id="9b024-288">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="9b024-289">Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet `$true`en de standaardwaarde is ).</span><span class="sxs-lookup"><span data-stu-id="9b024-289">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="9b024-290">De beschrijving is: Het beleid van de afdeling van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="9b024-290">The description is: Research department policy.</span></span>
- <span data-ttu-id="9b024-291">Hiermee wijzigt u de standaardactie voor spoofing in Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="9b024-291">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="9b024-292">Zie [Nieuw-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-292">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="9b024-293">Stap 2: PowerShell gebruiken om een anti-phish-regel te maken</span><span class="sxs-lookup"><span data-stu-id="9b024-293">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="9b024-294">Als u een anti-phish-regel wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-294">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="9b024-295">In dit voorbeeld wordt een anti-phish-regel met de naam Research Department met de volgende voorwaarden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="9b024-295">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="9b024-296">De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="9b024-296">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="9b024-297">De regel is van toepassing op leden van de groep met de naam Research Department.</span><span class="sxs-lookup"><span data-stu-id="9b024-297">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="9b024-298">Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9b024-298">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="9b024-299">Zie [Nieuw-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-299">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="9b024-300">PowerShell gebruiken om anti-phish-beleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="9b024-300">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="9b024-301">Als u bestaande anti-phish-beleidsregels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9b024-301">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9b024-302">In dit voorbeeld wordt een overzichtslijst geretourneerd van alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="9b024-302">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="9b024-303">In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="9b024-303">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="9b024-304">Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-304">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="9b024-305">PowerShell gebruiken om anti-phish-regels weer te geven</span><span class="sxs-lookup"><span data-stu-id="9b024-305">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="9b024-306">Als u bestaande anti-phish-regels wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9b024-306">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9b024-307">In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels geretourneerd, samen met de opgegeven eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="9b024-307">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="9b024-308">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="9b024-308">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="9b024-309">In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="9b024-309">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="9b024-310">Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-310">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="9b024-311">PowerShell gebruiken om anti-phish-beleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9b024-311">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="9b024-312">Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp een sectie [anti-phish-beleid te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)</span><span class="sxs-lookup"><span data-stu-id="9b024-312">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="9b024-313">De _Switch MakeDefault_ die het opgegeven beleid inschakelt in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="9b024-313">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="9b024-314">U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _parameter Naam)._</span><span class="sxs-lookup"><span data-stu-id="9b024-314">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9b024-315">Wanneer u de naam van een antiphishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel.</span><span class="sxs-lookup"><span data-stu-id="9b024-315">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="9b024-316">Als u een anti-phish-beleid wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-316">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9b024-317">Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-317">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="9b024-318">PowerShell gebruiken om anti-phish-regels te wijzigen</span><span class="sxs-lookup"><span data-stu-id="9b024-318">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="9b024-319">De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="9b024-319">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9b024-320">Zie de volgende sectie om bestaande anti-phish-regels in te schakelen of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="9b024-320">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="9b024-321">Anders zijn er geen aanvullende instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="9b024-321">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="9b024-322">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een sectie anti-phish-regel te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)</span><span class="sxs-lookup"><span data-stu-id="9b024-322">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="9b024-323">Als u een anti-phish-regel wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-323">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9b024-324">Zie [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="9b024-324">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="9b024-325">PowerShell gebruiken om anti-phish-regels in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="9b024-325">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="9b024-326">Het in- of uitschakelen van een anti-phish-regel in PowerShell schakelt of schakelt het hele anti-phishingbeleid in of uit (de anti-phish-regel en het toegewezen anti-phish-beleid).</span><span class="sxs-lookup"><span data-stu-id="9b024-326">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="9b024-327">U het standaard beleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="9b024-327">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="9b024-328">Gebruik de als volgt te houden of een anti-phish-regel in PowerShell in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="9b024-328">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="9b024-329">In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9b024-329">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9b024-330">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="9b024-330">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9b024-331">Zie [Inschakelen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-331">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="9b024-332">PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen</span><span class="sxs-lookup"><span data-stu-id="9b024-332">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="9b024-333">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="9b024-333">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9b024-334">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="9b024-334">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9b024-335">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9b024-335">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9b024-336">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="9b024-336">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9b024-337">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="9b024-337">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9b024-338">Als u de prioriteit van een anti-phish-regel in PowerShell wilt instellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="9b024-338">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9b024-339">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="9b024-339">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="9b024-340">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="9b024-340">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9b024-341">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="9b024-341">**Notes**:</span></span>

- <span data-ttu-id="9b024-342">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="9b024-342">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="9b024-343">Het standaard anti-phish-beleid heeft geen overeenkomstige anti-phish-regel en heeft altijd de onaanpasbare prioriteitswaarde **Laagste**.</span><span class="sxs-lookup"><span data-stu-id="9b024-343">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="9b024-344">PowerShell gebruiken om anti-phish-beleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="9b024-344">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="9b024-345">Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9b024-345">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="9b024-346">Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-346">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9b024-347">In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9b024-347">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9b024-348">Zie [Verwijderen-antiphishbeleid voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie .</span><span class="sxs-lookup"><span data-stu-id="9b024-348">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="9b024-349">PowerShell gebruiken om anti-phish-regels te verwijderen</span><span class="sxs-lookup"><span data-stu-id="9b024-349">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="9b024-350">Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9b024-350">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="9b024-351">Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="9b024-351">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="9b024-352">In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="9b024-352">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="9b024-353">Zie [Verwijderen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="9b024-353">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9b024-354">Hoe weet ik of deze procedures zijn geslaagd?</span><span class="sxs-lookup"><span data-stu-id="9b024-354">How do you know these procedures worked?</span></span>

<span data-ttu-id="9b024-355">Ga een van de volgende stappen uit om te controleren of u het ANTI-phishingbeleid van ATP hebt geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="9b024-355">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="9b024-356">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="9b024-356">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="9b024-357">Controleer de lijst met beleidsregels, hun **statuswaarden** en hun **prioriteitswaarden.**</span><span class="sxs-lookup"><span data-stu-id="9b024-357">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9b024-358">Ga als volgt te werk om meer details te bekijken:</span><span class="sxs-lookup"><span data-stu-id="9b024-358">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="9b024-359">Selecteer het beleid in de lijst en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="9b024-359">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="9b024-360">Klik **op Standaardbeleid** en bekijk de details in de flyout.</span><span class="sxs-lookup"><span data-stu-id="9b024-360">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="9b024-361">Vervang in \<Exchange Online\> PowerShell Naam door de naam van het beleid of de regel en voer de volgende opdracht uit en controleer de instellingen:</span><span class="sxs-lookup"><span data-stu-id="9b024-361">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
