---
title: Weergaven van campagnes in ATP
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
description: Meer informatie over campagneweergaven in Geavanceerde bedreigingsbeveiliging van Office 365.
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209593"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="3b2f2-103">Campagneweergaven in ATP</span><span class="sxs-lookup"><span data-stu-id="3b2f2-103">Campaign Views in ATP</span></span>

<span data-ttu-id="3b2f2-104">Campaign Views is een functie in Advanced Threat Protection (ATP) in het Security & Compliance Center dat phishing-aanvallen in de service identificeert en categoriseert.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="3b2f2-105">Campagneweergaven kunnen u helpen om:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="3b2f2-106">Efficiënt onderzoek en reageren op phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="3b2f2-107">Beter inzicht in de omvang van de aanval.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="3b2f2-108">Toon waarde aan besluitvormers.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-108">Show value to decision makers.</span></span>

<span data-ttu-id="3b2f2-109">Met campagneweergaven u het grote plaatje van een aanval sneller en completer zien dan welke mens dan ook.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="3b2f2-110">Wat is een campagne?</span><span class="sxs-lookup"><span data-stu-id="3b2f2-110">What is a campaign?</span></span>

<span data-ttu-id="3b2f2-111">Een campagne is een gecoördineerde e-mailaanval op een of meer organisaties.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="3b2f2-112">E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="3b2f2-113">Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om blijvend succes te garanderen.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="3b2f2-114">Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing, anti-spam en anti-malware gegevens over de hele dienst om te helpen bij het identificeren van campagnes.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="3b2f2-115">We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="3b2f2-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-116">For example:</span></span>

- <span data-ttu-id="3b2f2-117">**Aanvalsbron:** Bron-IP-adressen en e-maildomeinen van afzenders.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="3b2f2-118">**Eigenschappen van aanvalsberichten:** de inhoud, stijl en toon van de aanvalsberichten.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="3b2f2-119">**Ontvangers van aanvallen**: geadresseerde domeinen, geadresseerde functies (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privaat, enz.) en industrieën.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="3b2f2-120">**Attack payload:** Kwaadaardige links, bijlagen, of andere payloads in de aanval berichten.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="3b2f2-121">Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="3b2f2-122">Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="3b2f2-123">Campagne bekijkt het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3b2f2-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="3b2f2-124">Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **Management** \> **Campaigns**.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Campagneoverzicht in het Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="3b2f2-126">U ook naar de weergave Campagnes gaan vanaf:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="3b2f2-127">**Bedreigingsbeheer** \> **Explorer** \> **Bekijk** \> **Campagnes**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="3b2f2-128">**Bedreigingsbeheer** \> **Explorer** \> **Bekijk** \> **Alle e-mail** \> **Campagne**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="3b2f2-129">Als u geen campagnegegevens ziet, probeert u het datumbereik te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="3b2f2-130">Op de overzichtspagina vindt u de volgende informatie over de campagne:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="3b2f2-131">**Naam**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-131">**Name**</span></span>

- <span data-ttu-id="3b2f2-132">**Voorbeeldonderwerp**: de onderwerpregel van een van de berichten in de campagne.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="3b2f2-133">Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="3b2f2-134">**Type**: Momenteel is deze waarde altijd **Phish**.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="3b2f2-135">**Subtype**: Indien beschikbaar, het merk dat wordt phished door deze campagne.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="3b2f2-136">Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="3b2f2-137">**Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="3b2f2-138">**Inboxed:** het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan Junk).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="3b2f2-139">**Klik:** het aantal gebruikers dat op de URL in het phishingbericht heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="3b2f2-140">**Klikpercentage:** het percentage zoals berekend door "**Clicked**  /  **Klikinboxed**".</span><span class="sxs-lookup"><span data-stu-id="3b2f2-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="3b2f2-141">Deze waarde is een indicator van de effectiviteit van de campagne, en of de ontvangers in staat waren om het bericht te identificeren als phishing en te voorkomen dat te klikken op de payload URL.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="3b2f2-142">**Bezocht**: Hoeveel gebruikers daadwerkelijk maakte het door naar de payload website.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="3b2f2-143">Als er **klikwaarden** zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="3b2f2-144">Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="3b2f2-145">Campagnegegevens</span><span class="sxs-lookup"><span data-stu-id="3b2f2-145">Campaign details</span></span>

<span data-ttu-id="3b2f2-146">In de weergave campagnedetails is veel informatie beschikbaar over de campagne:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="3b2f2-147">Campagne-informatie:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-147">Campaign information:</span></span>

  - <span data-ttu-id="3b2f2-148">**ID:** de unieke campagne-id.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="3b2f2-149">**Gestart** en **beëindigd:** het datumbereikfilter dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="3b2f2-150">**Impact:** de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="3b2f2-151">Het totale aantal ontvangers.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-151">The total number of recipients.</span></span>

    - <span data-ttu-id="3b2f2-152">Het aantal berichten dat 'Inboxed' is (dat wil zeggen, geleverd aan de Postvak IN, niet aan Junk).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="3b2f2-153">Hoeveel gebruikers klikten op de URL payload in het phishing-bericht.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="3b2f2-154">Hoe veel gebruikers de URL hebben bezocht.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="3b2f2-155">Een tijdlijn van campagneactiviteit: wanneer de campagne is gestart en beëindigd en het aantal berichten in de loop van de tijd.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="3b2f2-156">Campagnestroom</span><span class="sxs-lookup"><span data-stu-id="3b2f2-156">Campaign flow</span></span>

<span data-ttu-id="3b2f2-157">Belangrijke details over de campagne worden weergegeven in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)_ in de sectie **Flow.**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="3b2f2-158">Deze gegevens helpen u inzicht te krijgen in de elementen van de campagne en de mogelijke impact in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Campagnegegevens die geen klikken op url-pagina's van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="3b2f2-160">Als u de plaats over een horizontale band in het diagram houdt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaald bron-IP, berichten van het bron-IP met behulp van het opgegeven afzenderdomein, enz.).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="3b2f2-161">Het diagram bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="3b2f2-162">**Afzender-IP's**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-162">**Sender IPs**</span></span>

- <span data-ttu-id="3b2f2-163">**Afzenderdomeinen**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-163">**Sender domains**</span></span>

- <span data-ttu-id="3b2f2-164">**Filter uitspraken:** De waarden hier zijn gerelateerd aan de beschikbare phishing en spam filteren vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="3b2f2-165">De beschikbare waarden worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="3b2f2-166">Value</span><span class="sxs-lookup"><span data-stu-id="3b2f2-166">Value</span></span>|<span data-ttu-id="3b2f2-167">Spam filter vonnis</span><span class="sxs-lookup"><span data-stu-id="3b2f2-167">Spam filter verdict</span></span>|<span data-ttu-id="3b2f2-168">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3b2f2-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="3b2f2-169">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="3b2f2-170">Het bericht is gemarkeerd als geen spam en/of het filteren van overgeslagen voordat het wordt beoordeeld door spamfiltering (bijvoorbeeld door een regel voor e-mailstroom, ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="3b2f2-171">Het bericht heeft spamfilters overgeslagen om andere redenen (de afzender en ontvanger lijken zich bijvoorbeeld in dezelfde organisatie te bevindt).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="3b2f2-172">**Geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="3b2f2-173">Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een regel voor e-mailstroom).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="3b2f2-174">**Gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="3b2f2-175">Het bericht is gemarkeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="3b2f2-176">**Niet gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="3b2f2-177">Het bericht is gemarkeerd als geen spam door spamte filteren.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="3b2f2-178">**Vrijgegeven**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="3b2f2-179">Het bericht heeft spamfilters overgeslagen omdat het is vrijgegeven uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="3b2f2-180">**Tenant toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="3b2f2-181">Het bericht heeft spamfilters overgeslagen vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="3b2f2-182">**Tenantblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="3b2f2-183">Het bericht is geblokkeerd door spamfiltering vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="3b2f2-184">**Gebruikerstoestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="3b2f2-185">Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="3b2f2-186">**Gebruikersblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="3b2f2-187">Het bericht is geblokkeerd door spamfilters omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="3b2f2-188">**Zap**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-188">**ZAP**</span></span>|<span data-ttu-id="3b2f2-189">N/a</span><span class="sxs-lookup"><span data-stu-id="3b2f2-189">n/a</span></span>|<span data-ttu-id="3b2f2-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) ondernam actie op het afgeleverde bericht volgens uw anti-spam beleidsinstellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).</span><span class="sxs-lookup"><span data-stu-id="3b2f2-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="3b2f2-191"><sup>\*</sup>Bekijk uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="3b2f2-192"><sup>\*\*</sup>Bekijk uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="3b2f2-193">**Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn geleverd (naar het Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de payload-URL in het bericht hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="3b2f2-194">U de in quarantaine geplaatste berichten ook uit quarantaine verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="3b2f2-195">Zie [In quarantaine geplaatste e-mailberichten in EOP](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="3b2f2-196">**Verwijderde map**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-196">**Deleted folder**</span></span>

  - <span data-ttu-id="3b2f2-197">**Gedaald**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-197">**Dropped**</span></span>

  - <span data-ttu-id="3b2f2-198">**Extern:** de ontvanger bevindt zich in uw on-premises e-mailorganisatie.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="3b2f2-199">**Mislukt**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-199">**Failed**</span></span>

  - <span data-ttu-id="3b2f2-200">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-200">**Forwarded**</span></span>

  - <span data-ttu-id="3b2f2-201">**Inbox**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-201">**Inbox**</span></span>

  - <span data-ttu-id="3b2f2-202">**Map ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-202">**Junk folder**</span></span>

  - <span data-ttu-id="3b2f2-203">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-203">**Quarantine**</span></span>

  - <span data-ttu-id="3b2f2-204">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="3b2f2-205">In alle lagen die meer dan 10 items bevatten, worden de bovenste 10 items weergegeven, terwijl de rest wordt gebundeld in **Anderen**.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="3b2f2-206">URL-klikken</span><span class="sxs-lookup"><span data-stu-id="3b2f2-206">URL clicks</span></span>

<span data-ttu-id="3b2f2-207">Wanneer een phishingbericht wordt bezorgd aan een ontvanger (naar de Inbox of de map Ongewenste e-mail), bestaat de kans dat de gebruiker op de payload-URL klikt.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="3b2f2-208">Niet klikken op de URL in een geleverd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="3b2f2-209">Als een gebruiker op de payload-URL in het phishingbericht heeft geklikt, worden de acties weergegeven in het **URL-klikgebied** van het diagram in de weergave campagnedetails.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="3b2f2-210">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-210">**Allowed**</span></span>

- <span data-ttu-id="3b2f2-211">**BlockPage:** De ontvanger klikte op de payload-URL, maar hun toegang tot de kwaadaardige website werd geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="3b2f2-212">**BlockPageOverride:** De ontvanger klikte op de payload URL in het bericht, ATP Safe Links geprobeerd om ze te stoppen, maar ze mochten het blok overschrijven.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="3b2f2-213">U moet uw [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis van veilige koppelingen mogen overschrijven en doorgaan naar de kwaadaardige website.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="3b2f2-214">**In afwachtingVanDetonationPage:** ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="3b2f2-215">**In afwachting vanDetonationPageOverride:** De ontvanger mocht het payload-ontploffingsproces overschrijven en de URL openen zonder op de resultaten te wachten.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="3b2f2-216">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="3b2f2-216">Tabs</span></span>

<span data-ttu-id="3b2f2-217">Er zijn verschillende tabbladen in de weergave campagnedetails waarmee u de campagne verder onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="3b2f2-218">**KLIKKEN OP URL:** Als gebruikers niet op de payload-URL in het phishingbericht hebben geklikt, is deze sectie leeg.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="3b2f2-219">Als een gebruiker op de URL heeft kunnen klikken, worden de volgende waarden ingevuld:</span><span class="sxs-lookup"><span data-stu-id="3b2f2-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="3b2f2-220">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="3b2f2-221">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="3b2f2-222">**Klik op Tijd**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-222">**Click Time**</span></span>

  - <span data-ttu-id="3b2f2-223">**Klik op Actie**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-223">**Click Action**</span></span>

- <span data-ttu-id="3b2f2-224">**Afzender-IP's**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-224">**Sender IPs**</span></span>

  - <span data-ttu-id="3b2f2-225">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="3b2f2-226">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-226">**Total Count**</span></span>

  - <span data-ttu-id="3b2f2-227">**Geteld invak**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="3b2f2-228">**Geblokkeerd aantal**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-228">**Blocked Count**</span></span>

  - <span data-ttu-id="3b2f2-229">**SPF Geslaagd**: De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="3b2f2-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="3b2f2-230">Een afzender die niet voldoet aan de SPF-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="3b2f2-231">**Afzenders**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-231">**Senders**</span></span>

  - <span data-ttu-id="3b2f2-232">**Afzender:** Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het Van: e-mailadres is dat gebruikers in hun e-mailclients zien.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="3b2f2-233">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-233">**Total Count**</span></span>

  - <span data-ttu-id="3b2f2-234">**Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-234">**Inboxed**</span></span>

  - <span data-ttu-id="3b2f2-235">**Niet inboxed**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="3b2f2-236">**DKIM Geslaagd**: De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="3b2f2-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="3b2f2-237">Een afzender die niet voldoet aan de DKIM-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="3b2f2-238">**DMARC Geslaagd**: De afzender is geverifieerd door [Domeinverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="3b2f2-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="3b2f2-239">Een afzender die niet voldoet aan de DMARC-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="3b2f2-240">**Payloads**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-240">**Payloads**</span></span>

  - <span data-ttu-id="3b2f2-241">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3b2f2-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="3b2f2-242">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="3b2f2-242">**Total Count**</span></span>

<span data-ttu-id="3b2f2-243"><sup>\*</sup>Als u op deze waarde klikt, wordt een nieuwe flyout geopend met meer details over het opgegeven item (gebruiker, URL, enz.) boven op de weergave campagnedetails.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="3b2f2-244">Als u wilt terugkeren naar de weergave campagnegegevens, klikt u op **Gereed** in de nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="3b2f2-245">Knoppen</span><span class="sxs-lookup"><span data-stu-id="3b2f2-245">Buttons</span></span>

<span data-ttu-id="3b2f2-246">Met de knoppen in de weergave campagnedetails u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="3b2f2-247">**Campagne verkennen:** hiermee opent u een nieuw zoektabblad van Threat Explorer met de waarde **Campagne-id** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="3b2f2-248">**Berichten in postvak in verkennen:** hiermee opent u een nieuw zoektabblad van Threat Explorer met de **locatie Campagne-id** en **weergave: Postvak IN** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="3b2f2-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
