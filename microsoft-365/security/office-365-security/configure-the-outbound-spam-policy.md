---
title: Uitgaande spamfilters configureren
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
description: Uitgaande spamfilters zijn altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail, waardoor organisaties worden beschermd die de service en de beoogde ontvangers gebruiken.
ms.openlocfilehash: 3800134855d42870992105e66313100ee0d77cd5
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081470"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="47d37-103">Uitgaande spamfilters configureren in Office 365</span><span class="sxs-lookup"><span data-stu-id="47d37-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="47d37-104">Als u een Office 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection(EOP)-klant zonder Exchange Online-postvakken, worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="47d37-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="47d37-105">Uitgaande spam van een gebruiker in uw organisatie duidt doorgaans op een gecompromitteerd account.</span><span class="sxs-lookup"><span data-stu-id="47d37-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="47d37-106">Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spamvertrouwensniveau of SCL) en worden door de [risicogroep](high-risk-delivery-pool-for-outbound-messages.md) geleid om de reputatie van de service te beschermen (dat wil zeggen, houd e-mailservers van Office 365-bron niet van IP-bloklijsten).</span><span class="sxs-lookup"><span data-stu-id="47d37-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="47d37-107">Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteiten en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="47d37-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="47d37-108">EOP gebruikt uitgaand spambeleid als onderdeel van de algehele verdediging van uw organisatie tegen spam.</span><span class="sxs-lookup"><span data-stu-id="47d37-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="47d37-109">Zie [Antispambeleid in Office 365](anti-spam-protection.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47d37-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="47d37-110">Beheerders kunnen het standaard uitgaande spambeleid bekijken, bewerken en configureren (maar niet verwijderen).</span><span class="sxs-lookup"><span data-stu-id="47d37-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="47d37-111">Voor een grotere granulariteit u ook aangepaste uitgaande spambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="47d37-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="47d37-112">Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="47d37-113">U uitgaand spambeleid configureren in het Office 365 Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Office 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="47d37-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="47d37-114">Uitgaand spambeleid in het Office 365 Security & Compliance Center vs Exchange Online PowerShell of Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="47d37-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="47d37-115">De basiselementen van een uitgaand spambeleid in EOP zijn:</span><span class="sxs-lookup"><span data-stu-id="47d37-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="47d37-116">**Het uitgaande spamfilterbeleid**: hiermee geeft u de acties op voor uitgaande spamfilteruitspraken en de meldingsopties.</span><span class="sxs-lookup"><span data-stu-id="47d37-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="47d37-117">**De regel voor uitgaand spamfilter**: hiermee geeft u de prioriteits- en ontvangerfilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="47d37-118">Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam-polities beheert in het Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="47d37-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="47d37-119">Wanneer u een uitgaand spambeleid maakt in het Security & Compliance Center, maakt u eigenlijk een uitgaande spamfilterregel en het bijbehorende uitgaande spamfilterbeleid tegelijkertijd met dezelfde naam voor beide.</span><span class="sxs-lookup"><span data-stu-id="47d37-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="47d37-120">Wanneer u een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor ontvangers de regel voor uitgaand spamfilter.</span><span class="sxs-lookup"><span data-stu-id="47d37-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="47d37-121">Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="47d37-122">Wanneer u een uitgaand spambeleid verwijdert uit het Security & Compliance Center, worden de regel voor uitgaand spamfilter en het bijbehorende uitgaande spamfilterbeleid verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47d37-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="47d37-123">In Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell is het verschil zichtbaar tussen uitgaand spamfilterbeleid en uitgaande spamfilterregels.</span><span class="sxs-lookup"><span data-stu-id="47d37-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="47d37-124">U beheert het beleid voor \*\* \*\*\* uitgaande spamfilters met behulp van de cmdlets -HostedContentFilterPolicy en u beheert uitgaande spamfilterregels met behulp van de \*\* \*cmdlets -HostedContentFilterRule.\*\*</span><span class="sxs-lookup"><span data-stu-id="47d37-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="47d37-125">In PowerShell maakt u eerst het uitgaande spamfilterbeleid en vervolgens maakt u de regel voor uitgaande spamfilters die het beleid identificeert waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="47d37-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="47d37-126">In PowerShell wijzigt u de instellingen in het uitgaande spamfilterbeleid en de regel voor uitgaand spamfilter afzonderlijk.</span><span class="sxs-lookup"><span data-stu-id="47d37-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="47d37-127">Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilters niet automatisch verwijderd en vice versa.</span><span class="sxs-lookup"><span data-stu-id="47d37-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="47d37-128">Standaard uitgaand spambeleid</span><span class="sxs-lookup"><span data-stu-id="47d37-128">Default outbound spam policy</span></span>

<span data-ttu-id="47d37-129">Elke organisatie heeft een ingebouwd uitgaand spambeleid met de naam Default dat de volgende eigenschappen heeft:</span><span class="sxs-lookup"><span data-stu-id="47d37-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="47d37-130">Het uitgaande spamfilterbeleid met de naam Standaard wordt toegepast op alle ontvangers in de organisatie, ook al is er geen uitgaande spamfilterregel (ontvangersfilters) gekoppeld aan het beleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="47d37-131">Het beleid met de naam Standaard heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast).</span><span class="sxs-lookup"><span data-stu-id="47d37-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="47d37-132">Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.</span><span class="sxs-lookup"><span data-stu-id="47d37-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="47d37-133">Het beleid met de naam Standaard is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="47d37-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="47d37-134">Om de effectiviteit van uitgaande spamfilters te vergroten, u aangepaste uitgaande spambeleidsregels maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="47d37-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47d37-135">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="47d37-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47d37-136">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="47d37-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="47d37-137">Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.</span><span class="sxs-lookup"><span data-stu-id="47d37-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="47d37-138">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47d37-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="47d37-139">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47d37-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="47d37-140">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="47d37-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="47d37-141">Als u uitgaande spambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="47d37-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="47d37-142">Voor alleen-lezen toegang tot uitgaande spambeleid moet u lid zijn van de rolgroep **Security Reader.**</span><span class="sxs-lookup"><span data-stu-id="47d37-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="47d37-143">Zie [Machtigingen in het Office 365-beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="47d37-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="47d37-144">Zie [EOP-instellingen](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)voor uitgaande spambeleid voor onze aanbevolen instellingen voor uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="47d37-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="47d37-145">Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **E-mailverzendlimiet overschreden**, **Verdachte e-mailverzendpatronen gedetecteerd**en **gebruiker beperkt van het verzenden van e-mail** berichten al e-mail meldingen te sturen naar leden van de **TenantAdmins** (**Global admins**) groep over ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers als gevolg van uitgaande spam.</span><span class="sxs-lookup"><span data-stu-id="47d37-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="47d37-146">Zie [De waarschuwingsinstellingen voor gebruikers met beperkte toegang verifiëren voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47d37-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="47d37-147">We raden u aan dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in uitgaand spambeleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="47d37-148">Gebruik het Security & Compliance Center om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="47d37-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="47d37-149">Als u een aangepast uitgaand spambeleid maakt in het Security & Compliance Center, wordt de spamfilterregel en het bijbehorende spamfilterbeleid tegelijkertijd met dezelfde naam voor beide gemaakt.</span><span class="sxs-lookup"><span data-stu-id="47d37-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="47d37-150">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-151">Klik op de pagina **Antispaminstellingen** op **Een uitgaand beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="47d37-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="47d37-152">Configureer de volgende instellingen in het **beleid voor uitgaand spamfilter** dat wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="47d37-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="47d37-153">**Naam**: een unieke beschrijvende naam voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="47d37-154">**Beschrijving**: voer een optionele beschrijving in voor het beleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="47d37-155">(Optioneel) Vouw de sectie **Meldingen** uit om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:</span><span class="sxs-lookup"><span data-stu-id="47d37-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="47d37-156">**Stuur een kopie van verdachte uitgaande e-mailberichten naar specifieke personen:** deze instelling voegt de opgegeven gebruikers als BCC-ontvangers toe aan de verdachte uitgaande berichten.</span><span class="sxs-lookup"><span data-stu-id="47d37-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="47d37-157">Ga als volgt te werk om deze instelling in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="47d37-157">To enable this setting:</span></span>

     <span data-ttu-id="47d37-158">a.</span><span class="sxs-lookup"><span data-stu-id="47d37-158">a.</span></span> <span data-ttu-id="47d37-159">Schakel het selectievakje in om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="47d37-160">b.</span><span class="sxs-lookup"><span data-stu-id="47d37-160">b.</span></span> <span data-ttu-id="47d37-161">Klik **op Personen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="47d37-161">Click **Add people**.</span></span> <span data-ttu-id="47d37-162">Ga als bedoeld als een flyout **voor geadresseerden toevoegen of verwijderen:**</span><span class="sxs-lookup"><span data-stu-id="47d37-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="47d37-163">C.</span><span class="sxs-lookup"><span data-stu-id="47d37-163">c.</span></span> <span data-ttu-id="47d37-164">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="47d37-164">Enter the sender's email address.</span></span> <span data-ttu-id="47d37-165">U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.</span><span class="sxs-lookup"><span data-stu-id="47d37-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="47d37-166">D.</span><span class="sxs-lookup"><span data-stu-id="47d37-166">d.</span></span> <span data-ttu-id="47d37-167">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="47d37-167">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="47d37-169">om de ontvangers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="47d37-169">to add the recipients.</span></span>

        <span data-ttu-id="47d37-170">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="47d37-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="47d37-171">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Adressenlijst** op de flyout.</span><span class="sxs-lookup"><span data-stu-id="47d37-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="47d37-172">Als u een ![geadresseerde](../../media/scc-remove-icon.png)wilt verwijderen, klikt u op Knop Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="47d37-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="47d37-173">E.</span><span class="sxs-lookup"><span data-stu-id="47d37-173">e.</span></span> <span data-ttu-id="47d37-174">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="47d37-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="47d37-175">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="47d37-176">**Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**</span><span class="sxs-lookup"><span data-stu-id="47d37-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="47d37-177">Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **Gebruiker met de naam Gebruiker die geen e-mail** verzendt, stuurt al e-mailmeldingen naar leden van de groep **TenantAdministrators** **(Globale beheerders)** wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie **Adressenlimieten.**</span><span class="sxs-lookup"><span data-stu-id="47d37-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="47d37-178">We raden u aan het waarschuwingsbeleid te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers hiervan op de hoogte te stellen.</span><span class="sxs-lookup"><span data-stu-id="47d37-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="47d37-179">Zie De [waarschuwingsinstellingen voor gebruikers met beperkte toegang controleren voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)instructies.</span><span class="sxs-lookup"><span data-stu-id="47d37-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="47d37-180">Ga als volgt te werk om deze instelling in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="47d37-180">To enable this setting:</span></span>

     <span data-ttu-id="47d37-181">a.</span><span class="sxs-lookup"><span data-stu-id="47d37-181">a.</span></span> <span data-ttu-id="47d37-182">Schakel het selectievakje in om de instelling in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="47d37-183">b.</span><span class="sxs-lookup"><span data-stu-id="47d37-183">b.</span></span> <span data-ttu-id="47d37-184">Klik **op Personen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="47d37-184">Click **Add people**.</span></span> <span data-ttu-id="47d37-185">Ga als bedoeld als een flyout **voor geadresseerden toevoegen of verwijderen:**</span><span class="sxs-lookup"><span data-stu-id="47d37-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="47d37-186">C.</span><span class="sxs-lookup"><span data-stu-id="47d37-186">c.</span></span> <span data-ttu-id="47d37-187">Voert u het e-mailadres van de afzender in.</span><span class="sxs-lookup"><span data-stu-id="47d37-187">Enter the sender's email address.</span></span> <span data-ttu-id="47d37-188">U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.</span><span class="sxs-lookup"><span data-stu-id="47d37-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="47d37-189">D.</span><span class="sxs-lookup"><span data-stu-id="47d37-189">d.</span></span> <span data-ttu-id="47d37-190">Klikt u op</span><span class="sxs-lookup"><span data-stu-id="47d37-190">Click</span></span> ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="47d37-192">om de ontvangers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="47d37-192">to add the recipients.</span></span>

        <span data-ttu-id="47d37-193">Herhaal deze stappen zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="47d37-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="47d37-194">De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Adressenlijst** op de flyout.</span><span class="sxs-lookup"><span data-stu-id="47d37-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="47d37-195">Als u een ![geadresseerde](../../media/scc-remove-icon.png)wilt verwijderen, klikt u op Knop Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="47d37-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="47d37-196">E.</span><span class="sxs-lookup"><span data-stu-id="47d37-196">e.</span></span> <span data-ttu-id="47d37-197">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="47d37-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="47d37-198">Schakel het selectievakje uit om deze instelling uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="47d37-199">(Optioneel) De sectie **Adressenlimieten** uitbreiden om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren: ]</span><span class="sxs-lookup"><span data-stu-id="47d37-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="47d37-200">**Maximum aantal ontvangers per gebruiker**</span><span class="sxs-lookup"><span data-stu-id="47d37-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="47d37-201">Een geldige waarde is 0 tot 10000.</span><span class="sxs-lookup"><span data-stu-id="47d37-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="47d37-202">De standaardwaarde is 0, wat betekent dat de standaardinstellingen van de service worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="47d37-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="47d37-203">Zie [Limieten verzenden voor office 365-opties voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47d37-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="47d37-204">**Externe uurlimiet**: Het maximum aantal externe ontvangers per uur.</span><span class="sxs-lookup"><span data-stu-id="47d37-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="47d37-205">**Interne uurlimiet**: Het maximum aantal interne ontvangers per uur.</span><span class="sxs-lookup"><span data-stu-id="47d37-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="47d37-206">**Dagelijkse limiet**: Het maximum aantal ontvangers per dag.</span><span class="sxs-lookup"><span data-stu-id="47d37-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="47d37-207">**Actie wanneer een gebruiker de bovenstaande limieten overschrijdt:** configureer de actie die moet worden uitgevoerd wanneer een van de limieten voor **geadresseerden** wordt overschreden.</span><span class="sxs-lookup"><span data-stu-id="47d37-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="47d37-208">Voor alle acties ontvangen de ontvangers die in de gebruiker zijn opgegeven **het verzenden van e-mailwaarschuwingsbeleid** (en in het nu overbodige **Melden specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spaminstellingen** in het uitgaande spambeleid, ontvangt u e-mailmeldingen.</span><span class="sxs-lookup"><span data-stu-id="47d37-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="47d37-209">**De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** Dit is de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="47d37-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="47d37-210">E-mailmeldingen worden verzonden en de gebruiker kan tot de volgende dag geen berichten meer verzenden, op basis van utc-tijd.</span><span class="sxs-lookup"><span data-stu-id="47d37-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="47d37-211">Er is geen manier voor de beheerder om dit blok te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="47d37-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="47d37-212">De activiteitswaarschuwing met de naam **Gebruiker die geen e-mail verzendt,** waarschuwt beheerders (via e-mail en op de pagina **Waarschuwingen weergeven).**</span><span class="sxs-lookup"><span data-stu-id="47d37-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="47d37-213">Alle ontvangers die zijn opgegeven in de **melding van specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spaminstellingen** in het beleid, worden ook op de hoogte gebracht.</span><span class="sxs-lookup"><span data-stu-id="47d37-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="47d37-214">De gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van utc-tijd.</span><span class="sxs-lookup"><span data-stu-id="47d37-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="47d37-215">Er is geen manier voor de beheerder om dit blok te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="47d37-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="47d37-216">**Beperk de gebruiker van het verzenden van e-mail:** E-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal \*\*[Beperkte gebruikers]<https://sip.protection.office.com/restrictedusers> \*\* in het Security & Compliance Center en de gebruiker kan geen e-mail verzenden totdat ze door een beheerder van de portal **Voor beperkte gebruikers** zijn verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt.</span><span class="sxs-lookup"><span data-stu-id="47d37-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="47d37-217">Zie Een [gebruiker verwijderen uit de portal voor beperkte gebruikers verwijderen na het verzenden van spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="47d37-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="47d37-218">**Geen actie, alleen alert:** E-mailmeldingen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="47d37-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="47d37-219">(Vereist) Vouw de sectie **Toegepast op uit** om de interne afzenders te identificeren waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="47d37-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="47d37-220">U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering.</span><span class="sxs-lookup"><span data-stu-id="47d37-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="47d37-221">Meerdere waarden met dezelfde voorwaarde of uitzondering gebruiken OR-logica (bijvoorbeeld _ \<afzender1\> _ of _ \<afzender2\>_).</span><span class="sxs-lookup"><span data-stu-id="47d37-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="47d37-222">Verschillende voorwaarden of uitzonderingen gebruiken AND-logica (bijvoorbeeld _ \<afzender1\> _ en _ \<lid van groep 1\>_).</span><span class="sxs-lookup"><span data-stu-id="47d37-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="47d37-223">Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="47d37-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="47d37-224">U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="47d37-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="47d37-225">**Het afzenderdomein is**: Hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="47d37-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="47d37-226">Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren.</span><span class="sxs-lookup"><span data-stu-id="47d37-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="47d37-227">Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="47d37-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="47d37-228">**Afzender is:** Hiermee geeft u een of meer gebruikers in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="47d37-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="47d37-229">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="47d37-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="47d37-230">Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="47d37-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="47d37-231">**Afzender is lid van**: Geeft een of meer groepen in uw organisatie op.</span><span class="sxs-lookup"><span data-stu-id="47d37-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="47d37-232">Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="47d37-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="47d37-233">Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.</span><span class="sxs-lookup"><span data-stu-id="47d37-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="47d37-234">**Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="47d37-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="47d37-235">De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="47d37-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="47d37-236">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="47d37-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="47d37-237">Het Beveiligings- & Compliance Center gebruiken om uitgaand spambeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="47d37-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="47d37-238">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-239">Klik op de pagina **Antispam-instellingen** op ![Pictogram](../../media/scc-expand-icon.png) Uitvouwen om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="47d37-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="47d37-240">Het standaardbeleid met de naam **Uitgaand spamfilterbeleid**.</span><span class="sxs-lookup"><span data-stu-id="47d37-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="47d37-241">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaand spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="47d37-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="47d37-242">De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u op **Beleid bewerken**klikken.</span><span class="sxs-lookup"><span data-stu-id="47d37-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="47d37-243">Het Beveiligingscentrum & Compliance Center gebruiken om uitgaand spambeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="47d37-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="47d37-244">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-245">Klik op de pagina **Antispam-instellingen** op ![Pictogram](../../media/scc-expand-icon.png) Uitvouwen om een uitgaand spambeleid uit te vouwen:</span><span class="sxs-lookup"><span data-stu-id="47d37-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="47d37-246">Het standaardbeleid met de naam **Uitgaand spamfilterbeleid**.</span><span class="sxs-lookup"><span data-stu-id="47d37-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="47d37-247">Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaand spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="47d37-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="47d37-248">Klik op **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="47d37-248">Click **Edit policy**.</span></span>

<span data-ttu-id="47d37-249">Voor aangepaste uitgaande spambeleidsregels zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan die welke zijn beschreven in het beveiligings& Compliance Center gebruiken om een gedeelte [over uitgaand spambeleid te maken.](#use-the-security--compliance-center-to-create-outbound-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="47d37-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="47d37-250">Voor het standaard uitgaande spambeleid met de naam **Uitgaand spamfilterbeleid**is de sectie **Toegepast op** niet beschikbaar (het beleid is voor iedereen van toepassing) en u de naam van het beleid niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="47d37-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="47d37-251">Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.</span><span class="sxs-lookup"><span data-stu-id="47d37-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="47d37-252">Uitgaand spambeleid in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="47d37-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="47d37-253">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-254">Klik op de pagina **Antispam-instellingen** op ![Pictogram Uitvouwen](../../media/scc-expand-icon.png) om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is Aangepast **uitgaand spambeleid).**</span><span class="sxs-lookup"><span data-stu-id="47d37-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="47d37-255">Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="47d37-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="47d37-256">Verplaats te wisselknop naar links om het beleid uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="47d37-256">Move the toggle to the left to disable the policy:</span></span> ![Uitschakelen](../../media/scc-toggle-off.png)

   <span data-ttu-id="47d37-258">Verplaats te wisselknop naar rechts om het beleid in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="47d37-258">Move the toggle to the right to enable the policy:</span></span> ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="47d37-260">U het standaard uitgaande spambeleid niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="47d37-261">De prioriteit instellen van aangepast uitgaand spambeleid</span><span class="sxs-lookup"><span data-stu-id="47d37-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="47d37-262">Uitgaand spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere politie's hebben een lagere prioriteit dan oudere beleidsregels).</span><span class="sxs-lookup"><span data-stu-id="47d37-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="47d37-263">Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit).</span><span class="sxs-lookup"><span data-stu-id="47d37-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="47d37-264">Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.</span><span class="sxs-lookup"><span data-stu-id="47d37-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="47d37-265">Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).</span><span class="sxs-lookup"><span data-stu-id="47d37-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="47d37-266">Het standaard uitgaande spambeleid met de naam **Uitgaand spamfilterbeleid** heeft de prioriteitswaarde **Laagste**en u deze niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="47d37-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="47d37-267">Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).</span><span class="sxs-lookup"><span data-stu-id="47d37-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="47d37-268">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-269">Zoek op de pagina **Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** **Aangepast uitgaand spambeleid**is.</span><span class="sxs-lookup"><span data-stu-id="47d37-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="47d37-270">Let op de waarden in de kolom **Prioriteit**:</span><span class="sxs-lookup"><span data-stu-id="47d37-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="47d37-271">Het aangepaste uitgaande spambeleid met de ![hoogste prioriteit](../../media/ITPro-EAC-DownArrowIcon.png) heeft het waarde pijl-omlaag-pictogram **0**.</span><span class="sxs-lookup"><span data-stu-id="47d37-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="47d37-272">Het aangepaste uitgaande spambeleid met de ![laagste prioriteit](../../media/ITPro-EAC-UpArrowIcon.png) heeft de ![waarde Omhoog](../../media/ITPro-EAC-UpArrowIcon.png) pijl-pictogram **n** (bijvoorbeeld pijl-omhoog-pictogram **3**).</span><span class="sxs-lookup"><span data-stu-id="47d37-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="47d37-273">Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, heeft ![het](../../media/ITPro-EAC-UpArrowIcon.png)![beleid tussen](../../media/ITPro-EAC-DownArrowIcon.png) de hoogste ![en laagste](../../media/ITPro-EAC-UpArrowIcon.png)![prioriteit](../../media/ITPro-EAC-DownArrowIcon.png) waarden Pictogram Pijl-omlaag **n** (bijvoorbeeld pictogram Pijl-omlaag **2**).</span><span class="sxs-lookup"><span data-stu-id="47d37-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="47d37-274">Klik op</span><span class="sxs-lookup"><span data-stu-id="47d37-274">Click</span></span> ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="47d37-276">of</span><span class="sxs-lookup"><span data-stu-id="47d37-276">or</span></span> ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="47d37-278">om het aangepaste uitgaande spambeleid omhoog of omlaag te verplaatsen in de prioriteitenlijst.</span><span class="sxs-lookup"><span data-stu-id="47d37-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="47d37-279">Het Beveiligings- & Compliance Center gebruiken om uitgaand spambeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="47d37-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="47d37-280">Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="47d37-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="47d37-281">Klik op de pagina **Antispam-instellingen** op ![Pictogram Uitvouwen](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **Type** is Aangepast **uitgaand spambeleid).**</span><span class="sxs-lookup"><span data-stu-id="47d37-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="47d37-282">Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="47d37-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="47d37-283">Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="47d37-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="47d37-284">U kunt het standaardbeleid niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="47d37-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="47d37-285">Exchange Online PowerShell of Exchange Online Protection PowerShell gebruiken om uitgaand spambeleid te configureren</span><span class="sxs-lookup"><span data-stu-id="47d37-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="47d37-286">PowerShell gebruiken om uitgaand spambeleid te maken</span><span class="sxs-lookup"><span data-stu-id="47d37-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="47d37-287">Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:</span><span class="sxs-lookup"><span data-stu-id="47d37-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="47d37-288">Maak het beleid voor uitgaande spamfilters.</span><span class="sxs-lookup"><span data-stu-id="47d37-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="47d37-289">Maak de regel voor uitgaand spamfilter die het uitgaande spamfilterbeleid opgeeft waarop de regel van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="47d37-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="47d37-290">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="47d37-290">**Notes**:</span></span>

- <span data-ttu-id="47d37-291">U een nieuwe regel voor uitgaande spamfilters maken en er een bestaand, niet-gekoppeld uitgaand spamfilterbeleid aan toewijzen.</span><span class="sxs-lookup"><span data-stu-id="47d37-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="47d37-292">Een regel voor uitgaande spamfilters kan niet worden gekoppeld aan meer dan één uitgaand spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="47d37-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="47d37-293">U de volgende instellingen configureren voor nieuwe uitgaande spamfilterbeleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings& Compliance Center nadat u het beleid hebt gemaakt:</span><span class="sxs-lookup"><span data-stu-id="47d37-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="47d37-294">Het nieuwe beleid als uitgeschakeld maken _(ingeschakeld_ `$false` op de cmdlet **Nieuw-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="47d37-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="47d37-295">Stel de prioriteit in van het beleid tijdens het maken ( _ \<Prioriteitsnummer\>_) op de cmdlet **Nieuw-HostedOutboundSpamFilterRule).** _Priority_</span><span class="sxs-lookup"><span data-stu-id="47d37-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="47d37-296">Een nieuw uitgaand spamfilterbeleid dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliance Center als u het beleid aan een spamfilterregel toewijst.</span><span class="sxs-lookup"><span data-stu-id="47d37-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="47d37-297">Stap 1: PowerShell gebruiken om een uitgaand spamfilterbeleid te maken</span><span class="sxs-lookup"><span data-stu-id="47d37-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="47d37-298">Als u een uitgaand spamfilterbeleid wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="47d37-299">In dit voorbeeld wordt een nieuw uitgaand spamfilterbeleid gemaakt met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="47d37-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="47d37-300">De limieten voor het aantal ontvangers zijn beperkt tot kleinere waarden die in de standaardwaarden worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="47d37-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="47d37-301">Zie [Limieten verzenden voor office 365-opties voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="47d37-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="47d37-302">Nadat een van de limieten is bereikt, kan de gebruiker geen berichten meer verzenden.</span><span class="sxs-lookup"><span data-stu-id="47d37-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="47d37-303">Zie [Nieuw gehostOutboundSpamFilterBeleid](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="47d37-304">Stap 2: PowerShell gebruiken om een uitgaande spamfilterregel te maken</span><span class="sxs-lookup"><span data-stu-id="47d37-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="47d37-305">Als u een regel voor uitgaand spamfilter wilt maken, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="47d37-306">In dit voorbeeld wordt een nieuwe uitgaande spamfilterregel gemaakt met de naam Contoso Executives met de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="47d37-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="47d37-307">Het uitgaande spamfilterbeleid met de naam Contoso Executives is gekoppeld aan de regel.</span><span class="sxs-lookup"><span data-stu-id="47d37-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="47d37-308">De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="47d37-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="47d37-309">Zie [Nieuw gehostESpamFilterRegel](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="47d37-310">PowerShell gebruiken om uitgaand spamfilterbeleid weer te geven</span><span class="sxs-lookup"><span data-stu-id="47d37-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="47d37-311">Voer de opdracht uit om een overzichtslijst met alle uitgaande spamfilterbeleidsregels terug te geven:</span><span class="sxs-lookup"><span data-stu-id="47d37-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="47d37-312">Als u gedetailleerde informatie over een specifiek uitgaand spamfilterbeleid wilt retourneren, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="47d37-313">In dit voorbeeld worden alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Executives geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="47d37-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="47d37-314">Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="47d37-315">PowerShell gebruiken om uitgaande spamfilterregels weer te geven</span><span class="sxs-lookup"><span data-stu-id="47d37-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="47d37-316">Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="47d37-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="47d37-317">Voer de opdracht uit om een overzichtslijst met alle uitgaande spamfilterregels terug te sturen:</span><span class="sxs-lookup"><span data-stu-id="47d37-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="47d37-318">Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:</span><span class="sxs-lookup"><span data-stu-id="47d37-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="47d37-319">Als u gedetailleerde informatie over een specifieke regel voor uitgaand spamfilter wilt retourneren, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="47d37-320">In dit voorbeeld worden alle eigenschapswaarden voor de uitgaande spamfilterregel met de naam Contoso Executives geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="47d37-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="47d37-321">Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="47d37-322">PowerShell gebruiken om uitgaand spamfilterbeleid te wijzigen</span><span class="sxs-lookup"><span data-stu-id="47d37-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="47d37-323">Dezelfde instellingen zijn beschikbaar wanneer u een beleid voor malwarefilters in PowerShell wijzigt, zoals wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp een gedeelte [over uitgaand beleid voor spamfilters te maken.](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)</span><span class="sxs-lookup"><span data-stu-id="47d37-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="47d37-324">**Opmerking:** U de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft geen _parameter Name)._</span><span class="sxs-lookup"><span data-stu-id="47d37-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="47d37-325">Wanneer u de naam van een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigt u alleen de naam van de regel voor uitgaande _spamfilters._</span><span class="sxs-lookup"><span data-stu-id="47d37-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="47d37-326">Als u een uitgaand spamfilterbeleid wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="47d37-327">Zie [Set-HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="47d37-328">PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen</span><span class="sxs-lookup"><span data-stu-id="47d37-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="47d37-329">De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilterregel in PowerShell wijzigt, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken.</span><span class="sxs-lookup"><span data-stu-id="47d37-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="47d37-330">Zie de volgende sectie om bestaande regels voor uitgaande spamfilters in te schakelen of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="47d37-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="47d37-331">Anders zijn er geen aanvullende instellingen beschikbaar wanneer u een uitgaande spamfilterregel in PowerShell wijzigt.</span><span class="sxs-lookup"><span data-stu-id="47d37-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="47d37-332">Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een regelsectie voor uitgaande spamfilters te maken.](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)</span><span class="sxs-lookup"><span data-stu-id="47d37-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="47d37-333">Als u een regel voor uitgaand spamfilter wilt wijzigen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="47d37-334">Zie [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="47d37-335">PowerShell gebruiken om regels voor uitgaande spamfilters in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="47d37-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="47d37-336">Als u een uitgaande spamfilterregel in PowerShell in- of uitschakelt, schakelt u het hele uitgaande spambeleid in of uit (de regel voor uitgaand spamfilter en het toegewezen uitgaande spamfilterbeleid).</span><span class="sxs-lookup"><span data-stu-id="47d37-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="47d37-337">U het standaard uitgaande spambeleid niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).</span><span class="sxs-lookup"><span data-stu-id="47d37-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="47d37-338">Gebruik de als volgt te houden om een regel voor uitgaand spamfilter in PowerShell in te schakelen of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="47d37-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="47d37-339">In dit voorbeeld wordt de regel voor het uitgaande spamfilter met de naam Marketing Department uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47d37-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="47d37-340">In dit voorbeeld wordt dezelfde regel ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="47d37-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="47d37-341">Zie [IngebouwdeSpamFilterRegel inschakelenEnen](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) [UitschakelenOutboundOfEnRegel en HostedOutboundSpamFilterRule uitschakelen voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="47d37-342">PowerShell gebruiken om de prioriteit van uitgaande spamfilterregels in te stellen</span><span class="sxs-lookup"><span data-stu-id="47d37-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="47d37-343">De hoogste prioriteit die u in kunt stellen op een regel is 0.</span><span class="sxs-lookup"><span data-stu-id="47d37-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="47d37-344">De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels.</span><span class="sxs-lookup"><span data-stu-id="47d37-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="47d37-345">Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="47d37-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="47d37-346">Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels.</span><span class="sxs-lookup"><span data-stu-id="47d37-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="47d37-347">Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.</span><span class="sxs-lookup"><span data-stu-id="47d37-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="47d37-348">Als u de prioriteit van een uitgaande spamfilterregel in PowerShell wilt instellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="47d37-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="47d37-349">In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2.</span><span class="sxs-lookup"><span data-stu-id="47d37-349">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="47d37-350">Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).</span><span class="sxs-lookup"><span data-stu-id="47d37-350">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="47d37-351">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="47d37-351">**Notes**:</span></span>

- <span data-ttu-id="47d37-352">Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Priority_ op de cmdlet **Nieuw-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="47d37-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="47d37-353">Het uitgaande standaardspamfilterbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de onaanpasbare prioriteitswaarde **Laagste**.</span><span class="sxs-lookup"><span data-stu-id="47d37-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="47d37-354">PowerShell gebruiken om uitgaand spamfilterbeleid te verwijderen</span><span class="sxs-lookup"><span data-stu-id="47d37-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="47d37-355">Wanneer u PowerShell gebruikt om een uitgaand spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor uitgaand spamfilter niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47d37-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="47d37-356">Als u een uitgaand spamfilterbeleid in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="47d37-357">In dit voorbeeld wordt het uitgaande spamfilterbeleid met de naam MarketingAfdeling verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47d37-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="47d37-358">Zie [Beleid verwijderen-gehostOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="47d37-359">PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen</span><span class="sxs-lookup"><span data-stu-id="47d37-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="47d37-360">Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende uitgaande spamfilterbeleid niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47d37-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="47d37-361">Als u een regel voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de als volgt:</span><span class="sxs-lookup"><span data-stu-id="47d37-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="47d37-362">In dit voorbeeld wordt de regel voor het uitgaande spamfilter met de naam Marketing Department verwijderd.</span><span class="sxs-lookup"><span data-stu-id="47d37-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="47d37-363">Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="47d37-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="47d37-364">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="47d37-364">For more information</span></span>

[<span data-ttu-id="47d37-365">Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Office 365</span><span class="sxs-lookup"><span data-stu-id="47d37-365">Remove blocked users from the Restricted Users portal in Office 365</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="47d37-366">Leveringspool met een hoog risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="47d37-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="47d37-367">Veelgestelde vragen over antispambescherming</span><span class="sxs-lookup"><span data-stu-id="47d37-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
