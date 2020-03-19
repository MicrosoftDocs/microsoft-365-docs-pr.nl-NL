---
title: Weergaven campagnes in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over campagneweergaven in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 40eab14dff8d0c51a35bfbc7a04365a5a025e207
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808824"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="211a6-103">Campagneweergaven in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="211a6-103">Campaign Views in Office 365 ATP</span></span>

<span data-ttu-id="211a6-104">Campagneweergaven is een functie in Advanced Threat Protection (ATP) in het Office 365 Security & Compliance Center die phishing-aanvallen in de service identificeert en categoriseert.</span><span class="sxs-lookup"><span data-stu-id="211a6-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="211a6-105">Campagneweergaven kunnen u helpen om:</span><span class="sxs-lookup"><span data-stu-id="211a6-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="211a6-106">Onderzoek en reageer efficiënt op phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="211a6-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="211a6-107">Beter begrijpen van de omvang van de aanval.</span><span class="sxs-lookup"><span data-stu-id="211a6-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="211a6-108">Toon waarde aan besluitvormers.</span><span class="sxs-lookup"><span data-stu-id="211a6-108">Show value to decision makers.</span></span>

<span data-ttu-id="211a6-109">Met campagneweergaven u het grote beeld van een aanval sneller en completer zien dan welke mens dan ook.</span><span class="sxs-lookup"><span data-stu-id="211a6-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="211a6-110">Wat is een campagne?</span><span class="sxs-lookup"><span data-stu-id="211a6-110">What is a campaign?</span></span>

<span data-ttu-id="211a6-111">Een campagne is een gecoördineerde e-mailaanval op een of meer organisaties.</span><span class="sxs-lookup"><span data-stu-id="211a6-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="211a6-112">E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie.</span><span class="sxs-lookup"><span data-stu-id="211a6-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="211a6-113">Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om verder succes te garanderen.</span><span class="sxs-lookup"><span data-stu-id="211a6-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="211a6-114">Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing-, anti-spam- en anti-malwaregegevens in de gehele Office 365-service om campagnes te identificeren.</span><span class="sxs-lookup"><span data-stu-id="211a6-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire Office 365 service to help identify campaigns.</span></span> <span data-ttu-id="211a6-115">We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren.</span><span class="sxs-lookup"><span data-stu-id="211a6-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="211a6-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="211a6-116">For example:</span></span>

- <span data-ttu-id="211a6-117">**Aanvalsbron**: Bron IP-adressen en e-maildomeinen van afzenders.</span><span class="sxs-lookup"><span data-stu-id="211a6-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="211a6-118">**Eigenschappen van aanvalsberichten:** de inhoud, stijl en toon van de aanvalsberichten.</span><span class="sxs-lookup"><span data-stu-id="211a6-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="211a6-119">**Aanvalsontvangers**: Geadresseerde functies, functies voor geadresseerden (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privé, enz.) en bedrijfstakken.</span><span class="sxs-lookup"><span data-stu-id="211a6-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="211a6-120">**Aanval payload:** Kwaadaardige links, bijlagen, of andere payloads in de aanval berichten.</span><span class="sxs-lookup"><span data-stu-id="211a6-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="211a6-121">Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden.</span><span class="sxs-lookup"><span data-stu-id="211a6-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="211a6-122">Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="211a6-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="211a6-123">Campagne bekijkt het Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="211a6-123">Campaign Views the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="211a6-124">Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **management** \> **Campaigns**.</span><span class="sxs-lookup"><span data-stu-id="211a6-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Campagneoverzicht in het Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="211a6-126">Je ook naar de campagneweergave gaan via:</span><span class="sxs-lookup"><span data-stu-id="211a6-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="211a6-127">**Campagne voor bedreigingsbeheer** \> \> **Explorer-weergave** \> **Campaigns** **Explorer**</span><span class="sxs-lookup"><span data-stu-id="211a6-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="211a6-128">**Bedreigingsbeheer** \> **Explorer** \> **Bekijk** \> **alle e-mailcampagne** \> **Campaign**</span><span class="sxs-lookup"><span data-stu-id="211a6-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="211a6-129">Als u geen campagnegegevens ziet, probeert u het datumbereik te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="211a6-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="211a6-130">Op de overzichtspagina vindt u de volgende informatie over de campagne:</span><span class="sxs-lookup"><span data-stu-id="211a6-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="211a6-131">**Naam**</span><span class="sxs-lookup"><span data-stu-id="211a6-131">**Name**</span></span>

- <span data-ttu-id="211a6-132">**Voorbeeldonderwerp**: De onderwerpregel van een van de berichten in de campagne.</span><span class="sxs-lookup"><span data-stu-id="211a6-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="211a6-133">Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.</span><span class="sxs-lookup"><span data-stu-id="211a6-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="211a6-134">**Type**: Momenteel is deze waarde altijd **Phish**.</span><span class="sxs-lookup"><span data-stu-id="211a6-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="211a6-135">**Subtype**: Waar beschikbaar, het merk dat wordt phished door deze campagne.</span><span class="sxs-lookup"><span data-stu-id="211a6-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="211a6-136">Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.</span><span class="sxs-lookup"><span data-stu-id="211a6-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="211a6-137">**Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.</span><span class="sxs-lookup"><span data-stu-id="211a6-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="211a6-138">**Inboxed**: Het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan Ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="211a6-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="211a6-139">**Klikte**: Het aantal gebruikers dat op de URL in het phishingbericht heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="211a6-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="211a6-140">**Klik op Frequentie**: Het percentage zoals berekend door "**Klikte** / **in boxed**".</span><span class="sxs-lookup"><span data-stu-id="211a6-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="211a6-141">Deze waarde is een indicator van de effectiviteit van de campagne en of de ontvangers het bericht als phishing konden identificeren en niet op de URL van de payload konden klikken.</span><span class="sxs-lookup"><span data-stu-id="211a6-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="211a6-142">**Bezocht**: Hoeveel gebruikers daadwerkelijk maakte het door naar de payload website.</span><span class="sxs-lookup"><span data-stu-id="211a6-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="211a6-143">Als er **klikwaarden** zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.</span><span class="sxs-lookup"><span data-stu-id="211a6-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="211a6-144">Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="211a6-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="211a6-145">Campagnegegevens</span><span class="sxs-lookup"><span data-stu-id="211a6-145">Campaign details</span></span>

<span data-ttu-id="211a6-146">In de weergave campagnedetails is veel informatie beschikbaar over de campagne:</span><span class="sxs-lookup"><span data-stu-id="211a6-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="211a6-147">Campagne-informatie:</span><span class="sxs-lookup"><span data-stu-id="211a6-147">Campaign information:</span></span>

  - <span data-ttu-id="211a6-148">**ID**: De unieke campagne-id.</span><span class="sxs-lookup"><span data-stu-id="211a6-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="211a6-149">**Gestart** en **beëindigd:** het datumbereikfilter dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="211a6-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="211a6-150">**Impact**: de volgende gegevens voor het geselecteerde datumbereikfilter:</span><span class="sxs-lookup"><span data-stu-id="211a6-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="211a6-151">Het totale aantal ontvangers.</span><span class="sxs-lookup"><span data-stu-id="211a6-151">The total number of recipients.</span></span>

    - <span data-ttu-id="211a6-152">Het aantal berichten dat "Inboxed" (dat wil zeggen, geleverd aan de Inbox, niet aan Junk).</span><span class="sxs-lookup"><span data-stu-id="211a6-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="211a6-153">Hoeveel gebruikers hebben op de URL-payload in het phishingbericht geklikt.</span><span class="sxs-lookup"><span data-stu-id="211a6-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="211a6-154">Hoeveel gebruikers de URL hebben bezocht.</span><span class="sxs-lookup"><span data-stu-id="211a6-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="211a6-155">Een tijdlijn van campagneactiviteit: wanneer de campagne is gestart en beëindigd, en het aantal berichten in de loop van de tijd.</span><span class="sxs-lookup"><span data-stu-id="211a6-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="211a6-156">Campagnestroom</span><span class="sxs-lookup"><span data-stu-id="211a6-156">Campaign flow</span></span>

<span data-ttu-id="211a6-157">Belangrijke details over de campagne worden weergegeven in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)_ in de sectie **Flow.**</span><span class="sxs-lookup"><span data-stu-id="211a6-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="211a6-158">Met deze gegevens u de elementen van de campagne en de mogelijke impact in uw organisatie begrijpen.</span><span class="sxs-lookup"><span data-stu-id="211a6-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Campagnegegevens die geen URL-klikken van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="211a6-160">Als u boven een horizontale band in het diagram zweeft, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaald bron-IP, berichten van het bron-IP-adres met behulp van het opgegeven afzenderdomein, enz.).</span><span class="sxs-lookup"><span data-stu-id="211a6-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="211a6-161">Het diagram bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="211a6-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="211a6-162">**Afzender-IP's**</span><span class="sxs-lookup"><span data-stu-id="211a6-162">**Sender IPs**</span></span>

- <span data-ttu-id="211a6-163">**Afzenderdomeinen**</span><span class="sxs-lookup"><span data-stu-id="211a6-163">**Sender domains**</span></span>

- <span data-ttu-id="211a6-164">**Filter vonnissen**: De waarden hier zijn gerelateerd aan de beschikbare phishing en spam filtering vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="211a6-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="211a6-165">De beschikbare waarden worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="211a6-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="211a6-166">Value</span><span class="sxs-lookup"><span data-stu-id="211a6-166">Value</span></span>|<span data-ttu-id="211a6-167">Het oordeel van het spamfilter</span><span class="sxs-lookup"><span data-stu-id="211a6-167">Spam filter verdict</span></span>|<span data-ttu-id="211a6-168">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="211a6-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="211a6-169">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="211a6-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="211a6-170">Het bericht werd gemarkeerd als niet spam en/of overgeslagen filtering voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een e-mailstroomregel, ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="211a6-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="211a6-171">Het bericht heeft spamfiltering om andere redenen overgeslagen (de afzender en ontvanger lijken bijvoorbeeld in dezelfde organisatie te zitten).</span><span class="sxs-lookup"><span data-stu-id="211a6-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="211a6-172">**Geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="211a6-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="211a6-173">Het bericht werd gemarkeerd als spam voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een e-mailstroomregel).</span><span class="sxs-lookup"><span data-stu-id="211a6-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="211a6-174">**Gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="211a6-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="211a6-175">Het bericht werd gemarkeerd als spam door spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="211a6-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="211a6-176">**Niet gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="211a6-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="211a6-177">Het bericht werd gemarkeerd als niet spam door spam filtering.</span><span class="sxs-lookup"><span data-stu-id="211a6-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="211a6-178">**Vrijgegeven**</span><span class="sxs-lookup"><span data-stu-id="211a6-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="211a6-179">Het bericht sloeg spamfiltering over omdat het uit quarantaine werd vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="211a6-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="211a6-180">**Tenant toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="211a6-181">Het bericht sloeg spamfiltering over vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="211a6-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="211a6-182">**Tenantblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="211a6-183">Het bericht werd geblokkeerd door spamfiltering vanwege anti-spambeleidsinstellingen (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="211a6-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="211a6-184">**Gebruikerstoestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="211a6-185">Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="211a6-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="211a6-186">**Gebruikersblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="211a6-187">Het bericht werd geblokkeerd door spamfiltering omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="211a6-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="211a6-188">**Zap**</span><span class="sxs-lookup"><span data-stu-id="211a6-188">**ZAP**</span></span>|<span data-ttu-id="211a6-189">N/a</span><span class="sxs-lookup"><span data-stu-id="211a6-189">n/a</span></span>|<span data-ttu-id="211a6-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) heeft actie ondernomen op het afgeleverde bericht volgens uw anti-spam beleid instellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).</span><span class="sxs-lookup"><span data-stu-id="211a6-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="211a6-191"><sup>\*</sup>Controleer uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service zou zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="211a6-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="211a6-192"><sup>\*\*</sup>Controleer uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="211a6-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="211a6-193">**Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn bezorgd (of aan de map Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de payload in het bericht hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="211a6-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="211a6-194">U ook de berichten in quarantaine verwijderen uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="211a6-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="211a6-195">Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="211a6-195">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="211a6-196">**Verwijderde map**</span><span class="sxs-lookup"><span data-stu-id="211a6-196">**Deleted folder**</span></span>

  - <span data-ttu-id="211a6-197">**Gedaald**</span><span class="sxs-lookup"><span data-stu-id="211a6-197">**Dropped**</span></span>

  - <span data-ttu-id="211a6-198">**Extern**: De ontvanger bevindt zich in uw on-premises e-mailorganisatie.</span><span class="sxs-lookup"><span data-stu-id="211a6-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="211a6-199">**Mislukt**</span><span class="sxs-lookup"><span data-stu-id="211a6-199">**Failed**</span></span>

  - <span data-ttu-id="211a6-200">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="211a6-200">**Forwarded**</span></span>

  - <span data-ttu-id="211a6-201">**Inbox**</span><span class="sxs-lookup"><span data-stu-id="211a6-201">**Inbox**</span></span>

  - <span data-ttu-id="211a6-202">**Map Ongewenste ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="211a6-202">**Junk folder**</span></span>

  - <span data-ttu-id="211a6-203">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="211a6-203">**Quarantine**</span></span>

  - <span data-ttu-id="211a6-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="211a6-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="211a6-205">In alle lagen die meer dan 10 items bevatten, worden de top 10 items weergegeven, terwijl de rest is gebundeld in **anderen.**</span><span class="sxs-lookup"><span data-stu-id="211a6-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="211a6-206">URL-klikken</span><span class="sxs-lookup"><span data-stu-id="211a6-206">URL clicks</span></span>

<span data-ttu-id="211a6-207">Wanneer een phishingbericht wordt bezorgd aan een ontvanger (in het Postvak IN of de map Ongewenste e-mail), is er altijd een kans dat de gebruiker op de URL van de payload klikt.</span><span class="sxs-lookup"><span data-stu-id="211a6-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="211a6-208">Niet klikken op de URL in een bezorgd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.</span><span class="sxs-lookup"><span data-stu-id="211a6-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="211a6-209">Als een gebruiker in het phishingbericht op de URL van de payload heeft geklikt, worden de acties weergegeven in het **URL-klikgebied** van het diagram in de weergave campagnedetails.</span><span class="sxs-lookup"><span data-stu-id="211a6-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="211a6-210">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="211a6-210">**Allowed**</span></span>

- <span data-ttu-id="211a6-211">**BlockPage:** De ontvanger klikte op de URL van de payload, maar zijn toegang tot de kwaadaardige website werd geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="211a6-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="211a6-212">**BlockPageOverride**: De ontvanger klikte op de url van de payload in het bericht, ATP Safe Links probeerde ze te stoppen, maar ze mochten het blok overschrijven.</span><span class="sxs-lookup"><span data-stu-id="211a6-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="211a6-213">U moet uw [beleid voor veilige links](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis veilige links mogen overschrijven en doorgaan naar de schadelijke website.</span><span class="sxs-lookup"><span data-stu-id="211a6-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="211a6-214">**PendingDetonationPage**: ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.</span><span class="sxs-lookup"><span data-stu-id="211a6-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="211a6-215">**PendingDetonationPageOverride**: De ontvanger mocht het ontnatieproces van payload's overschrijven en de URL openen zonder te wachten op de resultaten.</span><span class="sxs-lookup"><span data-stu-id="211a6-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="211a6-216">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="211a6-216">Tabs</span></span>

<span data-ttu-id="211a6-217">Er zijn verschillende tabbladen in de campagnedetailsweergave waarmee u de campagne verder onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="211a6-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="211a6-218">**URL-klikken:** als gebruikers niet op de URL van de payload in het phishingbericht hebben geklikt, is deze sectie leeg.</span><span class="sxs-lookup"><span data-stu-id="211a6-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="211a6-219">Als een gebruiker op de URL kon klikken, worden de volgende waarden ingevuld:</span><span class="sxs-lookup"><span data-stu-id="211a6-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="211a6-220">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="211a6-221">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="211a6-222">**Klik op Tijd**</span><span class="sxs-lookup"><span data-stu-id="211a6-222">**Click Time**</span></span>

  - <span data-ttu-id="211a6-223">**Klik op Actie**</span><span class="sxs-lookup"><span data-stu-id="211a6-223">**Click Action**</span></span>

- <span data-ttu-id="211a6-224">**Afzender-IP's**</span><span class="sxs-lookup"><span data-stu-id="211a6-224">**Sender IPs**</span></span>

  - <span data-ttu-id="211a6-225">**Afzender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="211a6-226">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="211a6-226">**Total Count**</span></span>

  - <span data-ttu-id="211a6-227">**Inboxed Tellen**</span><span class="sxs-lookup"><span data-stu-id="211a6-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="211a6-228">**Geblokkeerd aantal**</span><span class="sxs-lookup"><span data-stu-id="211a6-228">**Blocked Count**</span></span>

  - <span data-ttu-id="211a6-229">**SPF geslaagd:** De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="211a6-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="211a6-230">Een afzender die niet slaagt voor spf-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="211a6-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="211a6-231">**Afzenders**</span><span class="sxs-lookup"><span data-stu-id="211a6-231">**Senders**</span></span>

  - <span data-ttu-id="211a6-232">**Afzender**: Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het Van: e-mailadres is dat gebruikers in hun e-mailclients zien.</span><span class="sxs-lookup"><span data-stu-id="211a6-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="211a6-233">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="211a6-233">**Total Count**</span></span>

  - <span data-ttu-id="211a6-234">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="211a6-234">**Inboxed**</span></span>

  - <span data-ttu-id="211a6-235">**Niet inboxed**</span><span class="sxs-lookup"><span data-stu-id="211a6-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="211a6-236">**DKIM geslaagd:** De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="211a6-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="211a6-237">Een afzender die de DKIM-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="211a6-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="211a6-238">**DMARC geslaagd:** De afzender is geverifieerd door [domeingebaseerde berichtverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="211a6-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="211a6-239">Een afzender die de DMARC-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="211a6-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="211a6-240">**Payloads**</span><span class="sxs-lookup"><span data-stu-id="211a6-240">**Payloads**</span></span>

  - <span data-ttu-id="211a6-241">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="211a6-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="211a6-242">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="211a6-242">**Total Count**</span></span>

<span data-ttu-id="211a6-243"><sup>\*</sup>Als u op deze waarde klikt, wordt een nieuwe flyout geopend die meer details bevat over het opgegeven item (gebruiker, URL, enz.) bovenop de weergave campagnedetails.</span><span class="sxs-lookup"><span data-stu-id="211a6-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="211a6-244">Als u wilt terugkeren naar de weergave campagnedetails, klikt u op **Gereed** in de nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="211a6-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="211a6-245">Knoppen</span><span class="sxs-lookup"><span data-stu-id="211a6-245">Buttons</span></span>

<span data-ttu-id="211a6-246">Met de knoppen in de weergave campagnedetails u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="211a6-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="211a6-247">**Campagne verkennen:** hiermee opent u een nieuw zoektabblad Bedreigingverkenner met de waarde **Campagne-id** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="211a6-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="211a6-248">**Inboxed-berichten verkennen:** hiermee opent u een nieuw zoektabblad Bedreigingverkenner met de **locatie Campagne-id** en **levering: Postvak IN** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="211a6-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
