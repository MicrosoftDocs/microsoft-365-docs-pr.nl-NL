---
title: Scenario-spoof Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Beheerders kunnen inzicht krijgen in de werking van de spoof Intelligence-informatie. De persoon kan snel bepalen welke afzenders legitiem e-mail naar hun organisatie verzenden vanuit domeinen die geen e-mail verificatiecontroles doorgeven (SPF, DKIM of DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572739"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8b2a4-104">Scenario-spoof informatie inzicht in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="8b2a4-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8b2a4-105">In Microsoft 365-organisaties met Defender for Office 365 kunt u met behulp van de spoof Intelligence-informatie snel bepalen welke afzenders op de legitiem manier u niet-geverifieerde e-mailberichten (berichten van domeinen die geen SPF-, DKIM-of DMARC-controles doorgeven).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="8b2a4-106">Door bekende afzenders toe te staan vervalste berichten van bekende locaties te verzenden, kunt u foutberichten verminderen (goede e-mailberichten die als slecht zijn gemarkeerd).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="8b2a4-107">Door de toegestane vervalste afzenders te bewaken, geeft u een extra beveiligingslaag aan om te voorkomen dat onveilige berichten in uw organisatie arriveren.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="8b2a4-108">Zie [rapporten en inzichten in het beveiligings & nalevings centrum](reports-and-insights-in-security-and-compliance.md)voor meer informatie over rapporten en inzichten.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="8b2a4-109">Dit scenario is een van de verschillende voor het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="8b2a4-110">Zie de procedures in de sectie [Verwante onderwerpen](#related-topics) voor meer informatie over het navigeren in rapporten en inzichten.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b2a4-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="8b2a4-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b2a4-112">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8b2a4-113">Als u rechtstreeks naar de pagina **beveiligings dashboard** wilt gaan, gebruikt u <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="8b2a4-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="8b2a4-114">U kunt de spoof Intelligence-informatie van meer dan één dashboard bekijken in de beveiligings & compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="8b2a4-115">Ongeacht het dashboard dat u zoekt, biedt het inzicht dezelfde Details, zodat u snel dezelfde taken kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="8b2a4-116">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor beveiliging & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8b2a4-117">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="8b2a4-117">**Organization Management**</span></span>
  - <span data-ttu-id="8b2a4-118">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="8b2a4-118">**Security Administrator**</span></span>
  - <span data-ttu-id="8b2a4-119">**Beveiligings lezer**</span><span class="sxs-lookup"><span data-stu-id="8b2a4-119">**Security Reader**</span></span>
  - <span data-ttu-id="8b2a4-120">**Algemene lezer**</span><span class="sxs-lookup"><span data-stu-id="8b2a4-120">**Global Reader**</span></span>

  <span data-ttu-id="8b2a4-121">**Opmerking**: door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in de beveiligings & nalevings centrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8b2a4-122">Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="8b2a4-123">U schakelt spoof informatie in en uit in anti-phishing-beleid in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8b2a4-124">Zie [anti phishingberichten configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-124">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="8b2a4-125">Zie [spoof informatie configureren in Microsoft 365](learn-about-spoof-intelligence.md)als u wilt weten hoe u via spoof Intelligence afzenders kunt volgen en beheren die u niet-geverifieerde berichten verzendt.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-125">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="8b2a4-126">Open de informatie over spoof informatie in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="8b2a4-126">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="8b2a4-127">Ga in het beveiligings & nalevings centrum naar het dashboard **Threat Management** \> **.**</span><span class="sxs-lookup"><span data-stu-id="8b2a4-127">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="8b2a4-128">Ga naar de rij **inzichten** en zoek een van de volgende items:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-128">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="8b2a4-129">**Spoof Intelligence is ingeschakeld**: het inzicht is **in vervals bare domeinen die de authenticatie van de afgelopen 30 dagen mislukt**.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-129">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="8b2a4-130">Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-130">This is the default.</span></span>
   - <span data-ttu-id="8b2a4-131">**Spoof-informatie is uitgeschakeld**: de inzichten van de naam **spoofing inschakelen** en op de optie om spoof Intelligence in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-131">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="8b2a4-132">Het inzicht in het Dashboard toont u informatie zoals hier:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-132">The insight on the dashboard shows you information like this:</span></span>

   ![Schermafbeelding van spoof Intelligence Insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="8b2a4-134">Dit inzicht heeft in twee modi:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-134">This insight has two modes:</span></span>

   - <span data-ttu-id="8b2a4-135">Berekenings **modus**: als spoof Intelligence is ingeschakeld, ziet u in het voor inzicht hoe veel berichten werden beïnvloed door onze spoofberichten en de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="8b2a4-136">**Wat als-modus**: als spoof Intelligence is uitgeschakeld, kunt u in het inzicht zien hoeveel *berichten werden beïnvloed door* onze vervals Intelligence-mogelijkheden in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="8b2a4-137">In beide gevallen zijn de spoofende domeinen die worden weergegeven in het inzicht, onderverdeeld in twee categorieën: **verdachte domein paren** en **niet-verdachte domein paren**.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="8b2a4-138">Deze categorieën worden verder onderverdeeld in drie verschillende buckets om te worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-138">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="8b2a4-139">Een **domein paar** is een combinatie van het van-adres en de infrastructuur van verzenden:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-139">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="8b2a4-140">Het adres van de afzender is het e-mailadres dat wordt weergegeven in het vak van in e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-140">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="8b2a4-141">Dit adres wordt ook wel het `5322.From` adres genoemd.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="8b2a4-142">De verzendende infrastructuur, of afzender, is het organisatie domein van de omgekeerde DNS-zoekopdracht (PTR-record) van het verzendende IP-adres.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="8b2a4-143">Als het verzendende IP-adres geen PTR-record heeft, wordt de afzender geïdentificeerd door het versturen van IP met het 255.255.255.0-subnetmask in de CIDR-notatie (/24).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="8b2a4-144">Als bijvoorbeeld het IP-adres 192.168.100.100 is, is het volledige IP-adres van de afzender 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="8b2a4-145">**Verdachte domein paren** zijn:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="8b2a4-146">**Spoofing van hoge betrouwbaarheid**: op basis van de historische verplaatsings patronen en de reputatie Score van de domeinen, hebben we nadrukkelijk vertrouwen dat de domeinen wel spoofing zijn en dat berichten van deze domeinen waarschijnlijk schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-146">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="8b2a4-147">**Spoofing van matige betrouwbaarheid**: op basis van de historische Verstuur patronen en de reputatie Score van de domeinen, zijn er zeker van te zijn dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden, legitiem zijn.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-147">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="8b2a4-148">In deze categorie zijn er onjuiste positieve en onjuiste vertrouw baarheid van een spoof.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="8b2a4-149">**Niet-verdachte domein paren** (waaronder **herstel van spoofing**): het domein is vanwege expliciete verificatie van e-mail [verificatie gecontroleerd,](how-office-365-uses-spf-to-prevent-spoofing.md) [dkim](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-149">**Non-suspicious domain pairs** (includes **rescued spoof**): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="8b2a4-150">Het domein heeft echter wel verificatie gecontroleerd op impliciete e-mail verificatie ([samengestelde verificatie](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="8b2a4-151">Daarom is er geen anti-spoofing-actie uitgevoerd voor het bericht.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="8b2a4-152">Gedetailleerde informatie weergeven over verdachte domein paren van de spoof Intelligence Insight</span><span class="sxs-lookup"><span data-stu-id="8b2a4-152">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="8b2a4-153">Klik in het inzicht in de spoof Intelligence-informatie op een van de domein paren (hoog, normaal of hersteld).</span><span class="sxs-lookup"><span data-stu-id="8b2a4-153">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="8b2a4-154">De pagina **spoof Intelligence Insight** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-154">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="8b2a4-155">Op de pagina ziet u een lijst met afzenders die niet-geverifieerde e-mail naar uw organisatie verzenden.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-155">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="8b2a4-156">Met deze informatie kunt u bepalen of spoofing berichten worden geautoriseerd, of dat u verdere actie moet ondernemen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-156">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="8b2a4-157">U kunt de gegevens sorteren op aantal berichten, de datum waarop het spoof voor het laatst is gedetecteerd, en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="8b2a4-158">Selecteer een item in de tabel om een detaildeelvenster met uitgebreide informatie over het domein paar te openen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-158">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="8b2a4-159">De informatie omvat:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-159">The information includes:</span></span>
   - <span data-ttu-id="8b2a4-160">Waarom we dit hebben ondervangen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-160">Why we caught this.</span></span>
   - <span data-ttu-id="8b2a4-161">Wat u moet doen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-161">What you need to do.</span></span>
   - <span data-ttu-id="8b2a4-162">Een domein samenvatting.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-162">A domain summary.</span></span>
   - <span data-ttu-id="8b2a4-163">WhoIs gegevens over de afzender.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-163">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="8b2a4-164">Vergelijkbare berichten die we hebben weergegeven in uw Tenant van dezelfde afzender.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-164">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="8b2a4-165">U kunt hier ook voor kiezen om het domein paar toe te voegen of te verwijderen uit de lijst met veilige afzenders van **AllowedToSpoof** .</span><span class="sxs-lookup"><span data-stu-id="8b2a4-165">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Schermafbeelding van een domein in het detailvenster van de spoof Intelligence Insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="8b2a4-167">Een domein toevoegen aan of verwijderen uit de lijst met AllowedToSpoof</span><span class="sxs-lookup"><span data-stu-id="8b2a4-167">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="8b2a4-168">U kunt een domein toevoegen aan of verwijderen uit de lijst AllowedToSpoof (lijst met veilige afzenders) in het detailvenster van de spoof Intelligence-inzichten voor het domein paar.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-168">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="8b2a4-169">Zet de wisselknop dienovereenkomstig.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-169">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="8b2a4-170">Als u een domein paar toestaat, is de combinatie van het vervalste domein *en* de verstuurde infrastructuur alleen toegestaan.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-170">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="8b2a4-171">De e-mail van het vervalste domein van een bron wordt niet toegestaan, noch mag e-mail van de verzendende infrastructuur voor geen domeinen.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-171">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="8b2a4-172">U kunt bijvoorbeeld het volgende domein paar vervalste berichten in uw organisatie verzenden:</span><span class="sxs-lookup"><span data-stu-id="8b2a4-172">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="8b2a4-173">*Vervalste domein*: Gmail.com</span><span class="sxs-lookup"><span data-stu-id="8b2a4-173">*Spoofed Domain*: gmail.com"</span></span>
- <span data-ttu-id="8b2a4-174">*Infrastructuur verzenden* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="8b2a4-174">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="8b2a4-175">Alleen e-mailberichten van dit domein paar kunnen worden vervalst.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-175">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="8b2a4-176">Andere afzenders proberen te vervalsen gmail.com zijn niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-176">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="8b2a4-177">Berichten in andere domeinen van tms.mx.com zijn gecontroleerd via spoof Intelligence.</span><span class="sxs-lookup"><span data-stu-id="8b2a4-177">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b2a4-178">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8b2a4-178">Related topics</span></span>

[<span data-ttu-id="8b2a4-179">Anti-spoofing beveiliging in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b2a4-179">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
