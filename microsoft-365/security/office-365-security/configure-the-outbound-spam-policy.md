---
title: Filteren van uitgaande spam configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen in Exchange Online Protection (EOP) leren hoe ze uitgaand spambeleid kunnen bekijken, maken, wijzigen en verwijderen.
ms.openlocfilehash: 7102f858e0293f2a55fe68a55d4dc2cf3ab38a33
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024580"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="0f8ba-103">Uitgaande spamfiltering configureren in EOP</span><span class="sxs-lookup"><span data-stu-id="0f8ba-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="0f8ba-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendende activiteiten.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="0f8ba-105">Uitgaande spam van een gebruiker in uw organisatie duidt meestal op een gecompromitteerd account.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="0f8ba-106">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spamvertrouwensniveau of SCL) en worden doorgestuurd via de [leveringspool met een hoog risico](high-risk-delivery-pool-for-outbound-messages.md) om de reputatie van de service te beschermen (dat wil zeggen, houd Microsoft 365-brone-mailservers buiten IP-bloklijsten).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="0f8ba-107">Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteiten en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0f8ba-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="0f8ba-108">EOP gebruikt uitgaand spambeleid als onderdeel van de algehele verdediging van uw organisatie tegen spam.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="0f8ba-109">Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="0f8ba-110">Beheerders kunnen het standaard outbound spambeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="0f8ba-111">Voor meer granulariteit u ook aangepaste uitgaande spambeleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0f8ba-112">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0f8ba-113">U uitgaand spambeleid configureren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="0f8ba-114">Uitgaand spambeleid in het Security & Compliance Center vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f8ba-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="0f8ba-115">De basiselementen van een uitgaand spambeleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="0f8ba-116">**Het beleid voor uitgaande spamfilter:** geeft de acties op voor uitgaande spamfiltervonnten en de meldingsopties.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="0f8ba-117">**De regel van het uitgaande spamfilter:** hiermee geeft u de prioriteits- en ontvangerfilters op (op wie het beleid van toepassing is) voor een outbound spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="0f8ba-118">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spampolitie beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0f8ba-119">Wanneer u een uitgaand spambeleid maakt in het Security & Compliance Center, maakt u een uitgaande spamfilterregel en het bijbehorende beleid voor uitgaande spamfilter tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="0f8ba-120">Wanneer u een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en ontvangersfilters de regel van het uitgaande spamfilter.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="0f8ba-121">Alle andere instellingen wijzigen het bijbehorende outbound spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="0f8ba-122">Wanneer u een uitgaand spambeleid verwijdert uit het Security & Compliance Center, worden de regel voor uitgaande spamfilter en het bijbehorende beleid voor uitgaande spamfilters verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="0f8ba-123">In Exchange Online PowerShell of standalone EOP PowerShell is het verschil tussen het beleid voor uitgaande spamfilters en uitgaande regels voor spamfilters zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="0f8ba-124">U beheert uitgaande spamfilterbeleid met behulp van de cmdlets \*\* \* HostedOutboundSpamFilterPolicy\*\* en beheert uitgaande regels voor spamfilters met behulp van de cmdlets \*\* \* HostedOutboundSpamFilter.\*\*</span><span class="sxs-lookup"><span data-stu-id="0f8ba-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="0f8ba-125">In PowerShell maakt u eerst het beleid voor uitgaande spamfilters en vervolgens maakt u de regel voor uitgaande spamfilters die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="0f8ba-126">In PowerShell wijzigt u de instellingen in het beleid voor uitgaande spamfilters en de regel van het uitgaande spamfilter afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="0f8ba-127">Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilter niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="0f8ba-128">Standaard outbound spambeleid</span><span class="sxs-lookup"><span data-stu-id="0f8ba-128">Default outbound spam policy</span></span>

<span data-ttu-id="0f8ba-129">Elke organisatie heeft een ingebouwd outbound spambeleid met de naam Standaard met de volgende eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="0f8ba-130">Het uitgaande spamfilterbeleid met de naam Standaard wordt toegepast op alle ontvangers in de organisatie, ook al is er geen uitgaande spamfilterregel (geadresseerdefilters) die aan het beleid is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="0f8ba-131">Het beleid met de naam Standaard heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0f8ba-132">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="0f8ba-133">Het beleid met de naam Standaard is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0f8ba-134">Om de effectiviteit van uitgaande spamfiltering te vergroten, u aangepaste uitgaande spambeleid maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0f8ba-135">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0f8ba-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0f8ba-136">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0f8ba-137">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="0f8ba-138">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0f8ba-139">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0f8ba-140">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-140">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="0f8ba-141">Als u uitgaand spambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-141">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0f8ba-142">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-142">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0f8ba-143">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-143">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0f8ba-144">Voor alleen-lezen toegang tot uitgaand spambeleid moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-144">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0f8ba-145">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-145">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0f8ba-146">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-146">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="0f8ba-147">Zie Beleidsinstellingen voor [EOP-uitgaande spamfilters](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)voor onze aanbevolen instellingen voor uitgaande spambeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="0f8ba-148">Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **E-mail verzenden overschreden,** **Verdachte e-mailverzendpatronen gedetecteerd**en **Gebruiker beperkt van het verzenden van e-mail** al e-mail meldingen sturen naar leden van de **TenantAdmins** **(Global admins)** groep over ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers als gevolg van uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="0f8ba-149">Zie [De waarschuwingsinstellingen voor beperkte gebruikers verifiëren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="0f8ba-150">We raden u aan dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in het uitgaande spambeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="0f8ba-151">Gebruik het Security & Compliance Center om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="0f8ba-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="0f8ba-152">Als u een aangepast outbound spambeleid maakt in het Security & Compliance Center, worden tegelijkertijd de regel voor spamfilter en het bijbehorende spamfilterbeleid met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="0f8ba-153">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-154">Klik op de pagina **Antispam-instellingen** op **Een uitgaand beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="0f8ba-155">Configureer in het **beleid voor uitgaande spamfilters** dat wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="0f8ba-156">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0f8ba-157">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="0f8ba-158">(Optioneel) Vouw de sectie **Meldingen** uit om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="0f8ba-159">**Een kopie van verdachte uitgaande e-mailberichten verzenden naar specifieke personen:** met deze instelling worden de opgegeven gebruikers als BCC-ontvangers toegevoegd aan de verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0f8ba-160">Deze instelling werkt alleen in het standaard uitgaande spambeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="0f8ba-161">Het werkt niet in het aangepaste uitgaande spambeleid dat u maakt.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="0f8ba-162">Ga als volgt te werk om deze instelling in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-162">To enable this setting:</span></span>

     1. <span data-ttu-id="0f8ba-163">Schakel het selectievakje in om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="0f8ba-164">Klik **op Personen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-164">Click **Add people**.</span></span> <span data-ttu-id="0f8ba-165">In de flyout **voor geadresseerden toevoegen of verwijderen** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="0f8ba-166">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-166">Enter the sender's email address.</span></span> <span data-ttu-id="0f8ba-167">U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="0f8ba-168">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="0f8ba-168">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="0f8ba-170">om de ontvangers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-170">to add the recipients.</span></span>

        <span data-ttu-id="0f8ba-171">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="0f8ba-172">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Geadresseerdelijst** in de flyout.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="0f8ba-173">Als u een ontvanger wilt verwijderen, klikt u op ![ knop Verwijderen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="0f8ba-174">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="0f8ba-175">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="0f8ba-176">**Informeer specifieke personen als een afzender is geblokkeerd als gevolg van het verzenden van uitgaande spam:**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="0f8ba-177">Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **Gebruiker die is beperkt tot het verzenden van e-mail,** stuurt al e-mailmeldingen naar leden van de groep **TenantAdmins** **(Globale beheerders)** wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie **Geadresseerdelimieten.**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="0f8ba-178">We raden u aan het waarschuwingsbeleid te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="0f8ba-179">Zie De [waarschuwingsinstellingen voor beperkte gebruikers verifiëren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="0f8ba-180">Deze instelling werkt alleen in het standaard uitgaande spambeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-180">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="0f8ba-181">Het werkt niet in het aangepaste uitgaande spambeleid dat u maakt.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-181">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="0f8ba-182">Ga als volgt te werk om deze instelling in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-182">To enable this setting:</span></span>

     <span data-ttu-id="0f8ba-183">a.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-183">a.</span></span> <span data-ttu-id="0f8ba-184">Schakel het selectievakje in om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-184">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="0f8ba-185">b.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-185">b.</span></span> <span data-ttu-id="0f8ba-186">Klik **op Personen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-186">Click **Add people**.</span></span> <span data-ttu-id="0f8ba-187">In de flyout **voor geadresseerden toevoegen of verwijderen** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-187">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="0f8ba-188">c.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-188">c.</span></span> <span data-ttu-id="0f8ba-189">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-189">Enter the sender's email address.</span></span> <span data-ttu-id="0f8ba-190">U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-190">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="0f8ba-191">d.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-191">d.</span></span> <span data-ttu-id="0f8ba-192">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="0f8ba-192">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="0f8ba-194">om de ontvangers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-194">to add the recipients.</span></span>

        <span data-ttu-id="0f8ba-195">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-195">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="0f8ba-196">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Geadresseerdelijst** in de flyout.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-196">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="0f8ba-197">Als u een ontvanger wilt verwijderen, klikt u op ![ knop Verwijderen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-197">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="0f8ba-198">e.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-198">e.</span></span> <span data-ttu-id="0f8ba-199">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-199">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="0f8ba-200">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-200">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="0f8ba-201">(Optioneel) Vouw de sectie **Geadresseerdelimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-201">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="0f8ba-202">Deze instellingen zijn alleen van toepassing op postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-202">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="0f8ba-203">**Maximaal aantal ontvangers per gebruiker**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-203">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="0f8ba-204">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-204">A valid value is 0 to 10000.</span></span> <span data-ttu-id="0f8ba-205">De standaardwaarde is 0, wat betekent dat de standaardinstellingen voor de service worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-205">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="0f8ba-206">Zie [Limieten verzenden voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-206">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="0f8ba-207">**Externe uurlimiet**: Het maximum aantal externe ontvangers per uur.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-207">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="0f8ba-208">**Interne uurlimiet**: Het maximum aantal interne ontvangers per uur.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-208">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="0f8ba-209">**Daglimiet**: Het maximale totale aantal ontvangers per dag.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-209">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="0f8ba-210">**Actie wanneer een gebruiker de bovenstaande limieten overschrijdt:** Configureer de actie die u moet uitvoeren wanneer een van de **geadresseerdelimieten** wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-210">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="0f8ba-211">Voor alle acties mogen de ontvangers die zijn opgegeven in de **gebruiker geen e-mailwaarschuwingsbeleid verzenden** (en in het nu redundante Specifieke personen melden als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spamin** het uitgaande spambeleid, e-mailmeldingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-211">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="0f8ba-212">**Beperk de gebruiker van het verzenden van e-mail tot de volgende dag:** Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-212">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="0f8ba-213">E-mailmeldingen worden verzonden en de gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-213">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="0f8ba-214">Er is geen manier voor de beheerder om dit blok te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-214">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="0f8ba-215">De activiteitswaarschuwing met de naam **Gebruiker die geen e-mail mag verzenden,** waarschuwt beheerders (via e-mail en op de pagina **Waarschuwingen weergeven).**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-215">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="0f8ba-216">Alle ontvangers die zijn opgegeven in de **specifieke personen melden als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam-instelling** in het beleid, worden ook op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-216">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="0f8ba-217">De gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van UTC-tijd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-217">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="0f8ba-218">Er is geen manier voor de beheerder om dit blok te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-218">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="0f8ba-219">**Beperk de gebruiker van het verzenden van e-mail:** e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal \*\*[Beperkte gebruikers] <https://sip.protection.office.com/restrictedusers> \*\* in het Security & Compliance Center en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder uit de portal **Beperkte gebruikers** is verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker niet opnieuw beperkt voor die dag.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-219">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="0f8ba-220">Zie Een [gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-220">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="0f8ba-221">**Geen actie, alleen alert**: E-mailmeldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-221">**No action, alert only**: Email notifications are sent.</span></span>
6. <span data-ttu-id="0f8ba-222">(Optioneel) Vouw de sectie **Automatisch doorsturen** uit om besturingselementen te configureren over hoe automatisch doorsturen door gebruikers wordt beheerd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-222">(Optional) Expand **Automatic Forwarding** section to configure controls over how automatic forwarding by users is controlled.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0f8ba-223">Deze instellingen zijn alleen van toepassing op postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-223">These settings are only applicable to cloud-based mailboxes.</span></span>
   
   - <span data-ttu-id="0f8ba-224">**Automatisch doorsturen**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-224">**Automatic Forwarding**</span></span>
  
      <span data-ttu-id="0f8ba-225">Selecteer een van de opties om te bepalen hoe automatisch doorsturen wordt afgehandeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-225">Select one of the options to control how automatic forwarding is handled.</span></span>
    
      - <span data-ttu-id="0f8ba-226">**Automatisch**: standaardinstelling waarmee het systeem automatisch doorsturen kan regelen met automatisch doorsturen standaard uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-226">**Automatic**: Default setting that allows the system to control automatic forwarding with automatic forwarding disabled by default.</span></span>
      - <span data-ttu-id="0f8ba-227">**Op**: Extern doorsturen is onbeperkt ingeschakeld binnen het beleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-227">**On**: External forwarding is enabled within the policy without restriction.</span></span>
      - <span data-ttu-id="0f8ba-228">**Uit**: Extern doorsturen is uitgeschakeld en wordt geblokkeerd</span><span class="sxs-lookup"><span data-stu-id="0f8ba-228">**Off**: External forwarding is disabled and will be blocked</span></span>

7. <span data-ttu-id="0f8ba-229">(vereist) Vouw de sectie **Toegepast op** uit om de interne afzenders te identificeren waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-229">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="0f8ba-230">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-230">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0f8ba-231">Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-231">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="0f8ba-232">Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-232">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="0f8ba-233">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-233">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="0f8ba-234">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-234">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="0f8ba-235">**Het afzenderdomein is:** Hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-235">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="0f8ba-236">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-236">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="0f8ba-237">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-237">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="0f8ba-238">**Afzender is:** Hiermee geeft u een of meer gebruikers in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-238">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="0f8ba-239">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-239">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="0f8ba-240">Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-240">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="0f8ba-241">**Afzender is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-241">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="0f8ba-242">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-242">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="0f8ba-243">Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-243">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="0f8ba-244">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-244">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="0f8ba-245">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-245">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="0f8ba-246">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-246">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="0f8ba-247">Gebruik het Security & Compliance Center om uitgaand spambeleid te bekijken</span><span class="sxs-lookup"><span data-stu-id="0f8ba-247">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="0f8ba-248">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-249">Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="0f8ba-250">Het standaardbeleid met de naam **Uitgaande spamfilterbeleid**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-250">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="0f8ba-251">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-251">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="0f8ba-252">De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u op **Beleid bewerken**klikken.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-252">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="0f8ba-253">Gebruik het Security & Compliance Center om uitgaand spambeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-253">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="0f8ba-254">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-254">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-255">Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-255">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="0f8ba-256">Het standaardbeleid met de naam **Uitgaande spamfilterbeleid**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-256">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="0f8ba-257">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-257">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="0f8ba-258">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-258">Click **Edit policy**.</span></span>

<span data-ttu-id="0f8ba-259">Voor aangepaste uitgaande spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan die beschreven in de sectie [Beveiligingscentrum & Compliance om uitgaande spambeleid te maken.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="0f8ba-259">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="0f8ba-260">Voor het standaardbeleid voor uitgaande spam met de naam **Uitgaande spamfilterbeleid**is de sectie **Toegepast op** niet beschikbaar (het beleid is voor iedereen van toepassing) en u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-260">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="0f8ba-261">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-261">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="0f8ba-262">Uitgaand spambeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-262">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="0f8ba-263">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-264">Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is **aangepast uitgaand spambeleid).**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-264">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="0f8ba-265">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-265">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="0f8ba-266">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-266">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="0f8ba-268">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-268">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="0f8ba-270">U het standaardbeleid voor uitgaande spam niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-270">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="0f8ba-271">De prioriteit van het aangepaste uitgaande spambeleid instellen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-271">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="0f8ba-272">Het uitgaande spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere polities hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-272">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="0f8ba-273">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-273">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0f8ba-274">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-274">No two policies can have the same priority.</span></span>

<span data-ttu-id="0f8ba-275">Aangepaste uitgaande spambeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-275">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0f8ba-276">Het standaardvermelde spambeleid met de naam **Uitgaande spamfilterbeleid** heeft de **prioriteitswaarde Laagste**en u het niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-276">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="0f8ba-277">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-277">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="0f8ba-278">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-278">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-279">Zoek op de pagina **Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-279">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="0f8ba-280">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-280">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="0f8ba-281">Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft het ![ pictogram Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-281">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="0f8ba-282">Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft het ![ pictogram Pijl-omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijvoorbeeld ![ Omhoog Pijl-pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-282">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="0f8ba-283">Als u drie of meer aangepaste uitgaande spambeleid hebt, bevat het beleid tussen de hoogste en de laagste prioriteit het ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ pictogram Pijl-omhoog-pijl-omhoogpictogram ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (bijvoorbeeld ![ pictogram Pijl-omhoog-pijl-omlaag ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-283">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="0f8ba-284">Klik op</span><span class="sxs-lookup"><span data-stu-id="0f8ba-284">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="0f8ba-286">of</span><span class="sxs-lookup"><span data-stu-id="0f8ba-286">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="0f8ba-288">om het aangepaste uitgaande spambeleid omhoog of omlaag te verplaatsen in de prioriteitenlijst.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-288">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="0f8ba-289">Gebruik het Security & Compliance Center om uitgaande spambeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-289">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="0f8ba-290">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-290">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f8ba-291">Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **Type** is **aangepast uitgaand spambeleid).**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-291">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="0f8ba-292">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-292">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="0f8ba-293">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-293">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0f8ba-294">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-294">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="0f8ba-295">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="0f8ba-295">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="0f8ba-296">PowerShell gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="0f8ba-296">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="0f8ba-297">Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-297">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0f8ba-298">Maak het beleid voor uitgaande spamfilters.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-298">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="0f8ba-299">Maak de regel voor uitgaande spamfilters die het uitgaande spamfilterbeleid opgeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-299">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="0f8ba-300">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-300">**Notes**:</span></span>

- <span data-ttu-id="0f8ba-301">U een nieuwe regel voor uitgaande spamfilters maken en er een bestaand, niet-gekoppeld outbound spamfilterbeleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-301">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="0f8ba-302">Een uitgaande spamfilterregel kan niet worden gekoppeld aan meer dan één outbound spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-302">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="0f8ba-303">U de volgende instellingen configureren voor nieuw beleid voor uitgaande spamfilters in PowerShell dat pas beschikbaar is in het Security & Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-303">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0f8ba-304">Maak het nieuwe beleid als uitgeschakeld (_Ingeschakeld_ `$false` op de cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-304">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="0f8ba-305">Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-305">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="0f8ba-306">Een nieuw beleid voor uitgaande spamfilters dat u maakt in PowerShell, is pas zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een spamfilterregel.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-306">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="0f8ba-307">Stap 1: PowerShell gebruiken om een outbound spamfilterbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="0f8ba-307">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="0f8ba-308">Als u een beleid voor uitgaande spamfilters wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-308">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0f8ba-309">In dit voorbeeld wordt een nieuw beleid voor uitgaande spamfilters gemaakt met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-309">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="0f8ba-310">De tarieflimieten voor ontvangers zijn beperkt tot kleinere waarden die de standaardwaarden hebben.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-310">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="0f8ba-311">Zie [Limieten verzenden voor Microsoft 365-opties](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-311">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="0f8ba-312">Nadat een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-312">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="0f8ba-313">Zie [Nieuw-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-313">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="0f8ba-314">Stap 2: PowerShell gebruiken om een regel voor uitgaande spamfilters te maken</span><span class="sxs-lookup"><span data-stu-id="0f8ba-314">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="0f8ba-315">Als u een regel voor uitgaande spamfilter wilt maken, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-315">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0f8ba-316">In dit voorbeeld wordt een nieuwe regel voor uitgaande spamfilters gemaakt met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-316">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="0f8ba-317">Het uitgaande spamfilterbeleid met de naam Contoso Executives is gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-317">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="0f8ba-318">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-318">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="0f8ba-319">Zie [Nieuw-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-319">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="0f8ba-320">PowerShell gebruiken om het beleid voor uitgaande spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="0f8ba-320">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="0f8ba-321">Voer deze opdracht uit om een overzichtslijst met alle uitgaande spamfilterregels terug te sturen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-321">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="0f8ba-322">Als u gedetailleerde informatie over een specifiek beleid voor uitgaande spamfilters wilt retourneren, gebruikt u de syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-322">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="0f8ba-323">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor het beleid voor uitgaande spamfilter met de naam Leidinggevenden.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-323">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="0f8ba-324">Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-324">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="0f8ba-325">PowerShell gebruiken om uitgaande regels voor spamfilters weer te geven</span><span class="sxs-lookup"><span data-stu-id="0f8ba-325">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="0f8ba-326">Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-326">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="0f8ba-327">Voer deze opdracht uit om een overzichtslijst met alle regels voor uitgaande spamfilters terug te sturen:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-327">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="0f8ba-328">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-328">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="0f8ba-329">Als u gedetailleerde informatie over een specifieke regel voor uitgaande spamfilter wilt retourneren, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-329">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="0f8ba-330">In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor de regel voor het uitgaande spamfilter met de naam Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-330">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="0f8ba-331">Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-331">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="0f8ba-332">PowerShell gebruiken om het beleid voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-332">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="0f8ba-333">Dezelfde instellingen zijn beschikbaar wanneer u een beleid voor malwarefilters wijzigt in PowerShell als wanneer u het beleid maakt zoals beschreven in [stap 1: PowerShell gebruiken om](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) eerder in dit onderwerp een uitgaande sectie voor spamfilterbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-333">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="0f8ba-334">U de naam van een outbound spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft geen parameter _Name)._</span><span class="sxs-lookup"><span data-stu-id="0f8ba-334">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0f8ba-335">Wanneer u de naam van een uitgaande spambeleid wijzigt in het Security & Compliance Center, wijzigt u alleen de _regel_van het uitgaande spamfilter .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-335">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="0f8ba-336">Als u een beleid voor uitgaande spamfilters wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-336">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0f8ba-337">Zie [Set-HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-337">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="0f8ba-338">PowerShell gebruiken om de regels voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-338">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="0f8ba-339">De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilterregel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-339">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0f8ba-340">Zie de volgende sectie om bestaande regels voor uitgaande spamfilters in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-340">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="0f8ba-341">Anders zijn er geen extra instellingen beschikbaar wanneer u een regel voor uitgaande spamfilters wijzigt in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-341">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="0f8ba-342">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een regelsectie voor uitgaande spamfilters te maken.](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)</span><span class="sxs-lookup"><span data-stu-id="0f8ba-342">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0f8ba-343">Als u een regel voor uitgaande spamfilters wilt wijzigen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-343">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0f8ba-344">Zie [Set-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-344">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="0f8ba-345">PowerShell gebruiken om regels voor uitgaande spamfilter in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-345">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="0f8ba-346">Als u een uitgaande spamfilterregel inschakelt of uitschakelt in PowerShell, wordt het hele uitgaande spambeleid (de regel van het uitgaande spamfilter en het toegewezen outbound spamfilterbeleid) in- of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-346">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="0f8ba-347">U het standaard uitgaande spambeleid niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-347">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="0f8ba-348">Als u een regel voor uitgaande spamfilters in PowerShell wilt in- of uitschakelen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-348">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="0f8ba-349">In dit voorbeeld wordt de regel voor uitgaande spamfilter marketing uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-349">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="0f8ba-350">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-350">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="0f8ba-351">Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [HostedOutboundSpamFilterRule uitschakelen](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-351">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="0f8ba-352">PowerShell gebruiken om de prioriteit van regels voor uitgaande spamfilters in te stellen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-352">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="0f8ba-353">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-353">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0f8ba-354">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-354">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0f8ba-355">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-355">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0f8ba-356">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-356">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0f8ba-357">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-357">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0f8ba-358">Als u de prioriteit van een regel voor uitgaande spamfilters wilt instellen in PowerShell, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-358">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0f8ba-359">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-359">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0f8ba-360">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="0f8ba-360">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 
> - <span data-ttu-id="0f8ba-361">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="0f8ba-361">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="0f8ba-362">Het uitgaande standaardspamfilterbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifiable **prioriteitswaarde Laagste**.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-362">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="0f8ba-363">PowerShell gebruiken om het beleid voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-363">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="0f8ba-364">Wanneer u PowerShell gebruikt om een outbound spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor uitgaande spamfilters niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-364">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="0f8ba-365">Als u een beleid voor uitgaande spamfilters in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-365">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0f8ba-366">In dit voorbeeld wordt het beleid voor uitgaande spamfilter met de naam Marketing department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-366">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0f8ba-367">Zie [Remove-HostedOutboundSpamFilterPolicy verwijderen](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-367">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="0f8ba-368">PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="0f8ba-368">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="0f8ba-369">Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor uitgaande spamfilters niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-369">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="0f8ba-370">Als u een regel voor uitgaande spamfilters in PowerShell wilt verwijderen, gebruikt u deze syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0f8ba-370">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="0f8ba-371">In dit voorbeeld wordt de regel voor uitgaande spamfilter marketing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0f8ba-371">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="0f8ba-372">Zie [Remove-HostedOutboundSpamFilterRule verwijderen](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .</span><span class="sxs-lookup"><span data-stu-id="0f8ba-372">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="0f8ba-373">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="0f8ba-373">For more information</span></span>

[<span data-ttu-id="0f8ba-374">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten</span><span class="sxs-lookup"><span data-stu-id="0f8ba-374">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="0f8ba-375">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="0f8ba-375">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="0f8ba-376">Veelgestelde vragen over beveiliging tegen ongewenste e-mail</span><span class="sxs-lookup"><span data-stu-id="0f8ba-376">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="0f8ba-377">Rapport over automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="0f8ba-377">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
