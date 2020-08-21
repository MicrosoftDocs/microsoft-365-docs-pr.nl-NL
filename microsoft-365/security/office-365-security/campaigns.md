---
title: Campagne weergaven in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over campagne weergaven in Office 365 Advanced Threat Protection.
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825795"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="805ba-103">Campagne weergaven in ATP</span><span class="sxs-lookup"><span data-stu-id="805ba-103">Campaign Views in ATP</span></span>

<span data-ttu-id="805ba-104">Voorbeeld van een campagne is een functie in de weergave Advanced Threat Protection (ATP) in het beveiligings & nalevings centrum waarmee phishing-aanvallen in de service worden geïdentificeerd en gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="805ba-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="805ba-105">Met behulp van campagne weergaven kunt u:</span><span class="sxs-lookup"><span data-stu-id="805ba-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="805ba-106">Onderzoek een efficiënt onderzoek en reageer op een malafide aanval.</span><span class="sxs-lookup"><span data-stu-id="805ba-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="805ba-107">Beter inzicht in het reikwijdte van de aanval.</span><span class="sxs-lookup"><span data-stu-id="805ba-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="805ba-108">Waarde weergeven voor beslissers.</span><span class="sxs-lookup"><span data-stu-id="805ba-108">Show value to decision makers.</span></span>

<span data-ttu-id="805ba-109">Met campagne weergaven kunt u de grote afbeelding van een aanval sneller en helemaal compleet zien.</span><span class="sxs-lookup"><span data-stu-id="805ba-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="805ba-110">Wat is een campagne?</span><span class="sxs-lookup"><span data-stu-id="805ba-110">What is a campaign?</span></span>

<span data-ttu-id="805ba-111">Een campagne is een gecoördineerde aanval van een e-mailbericht voor een of meer organisaties.</span><span class="sxs-lookup"><span data-stu-id="805ba-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="805ba-112">E-mail aanvallen waarmee referenties en bedrijfsgegevens worden gestolen, bestaan uit een grote en lucrative-branche.</span><span class="sxs-lookup"><span data-stu-id="805ba-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="805ba-113">Aangezien technologieën in een inspanning toenemen, wijzigen ze hun methoden in een inspanning om ervoor te zorgen dat ze succes oplopen.</span><span class="sxs-lookup"><span data-stu-id="805ba-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="805ba-114">Microsoft profiteert van de enorme hoeveelheid anti-phishing, anti-spam en bescherming tegen malware via de volledige service, zodat u campagnes kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="805ba-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="805ba-115">We analyseren en classificeren de informatie over aanvallen op basis van diverse factoren.</span><span class="sxs-lookup"><span data-stu-id="805ba-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="805ba-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="805ba-116">For example:</span></span>

- <span data-ttu-id="805ba-117">**Schadelijke bron**: de bron-IP-adressen en de e-mail domeinen van de afzender.</span><span class="sxs-lookup"><span data-stu-id="805ba-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="805ba-118">**Eigenschappen van een aanvals bericht**: de inhoud, stijl en Toon van de berichten.</span><span class="sxs-lookup"><span data-stu-id="805ba-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="805ba-119">**Geadresseerden voor aanvallen**: domeinen van de ontvanger, de taakfuncties van de geadresseerde (beheerders, leidinggevenden, enzovoort), bedrijfstypen (groot, klein, openbaar, privé, enzovoort) en industrieën.</span><span class="sxs-lookup"><span data-stu-id="805ba-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="805ba-120">**Nettolading**van een aanval: kwaadaardige koppelingen, bijlagen of andere nettoladingen in de berichten.</span><span class="sxs-lookup"><span data-stu-id="805ba-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="805ba-121">Een campagne kan korte tijd in beslag nemen of meerdere dagen, weken of maanden belopen met actieve en niet-actieve perioden.</span><span class="sxs-lookup"><span data-stu-id="805ba-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="805ba-122">Er kan een campagne worden gestart voor uw specifieke organisatie of uw organisatie maakt deel uit van een grotere campagne in meerdere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="805ba-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="805ba-123">Campagne weergeven & nalevings centrum voor beveiliging</span><span class="sxs-lookup"><span data-stu-id="805ba-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="805ba-124">De weergave campagne is beschikbaar in het [beveiligings & compliance](https://protection.office.com) van een **Threat Management** \> **Campaigns**-campagne, of direct op <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="805ba-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Overzicht van campagnes in het nalevings centrum voor beveiligings &](../../media/campaigns-overview.png)

<span data-ttu-id="805ba-126">U kunt ook weergave van de campagne bekijken:</span><span class="sxs-lookup"><span data-stu-id="805ba-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="805ba-127">**Threat Management** \> **Verkenner** \> **Weergave** \> Een **campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="805ba-128">**Threat Management** \> **Verkenner** \> **Weergave** \> **Alle e-mailberichten** \> Tabblad **campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="805ba-129">**Threat Management** \> **Verkenner** \> **Weergave** \> **Phishing** \> Tabblad **campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="805ba-130">**Threat Management** \> **Verkenner** \> **Weergave** \> **Malware** \> Tabblad **campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="805ba-131">Voor de weergave van een campagne moet u lid zijn van de rollen groepen **Organisatiebeheer**, **beveiliging beheerder**of **beveiligings lezer** in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="805ba-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="805ba-132">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="805ba-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="805ba-133">Overzicht van campagnes</span><span class="sxs-lookup"><span data-stu-id="805ba-133">Campaigns overview</span></span>

<span data-ttu-id="805ba-134">Op de pagina overzicht vindt u informatie over alle campagnes.</span><span class="sxs-lookup"><span data-stu-id="805ba-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="805ba-135">Op het tabblad standaard **campagne** wordt in het gebied **type campagne** een staafdiagram weergegeven met het aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="805ba-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="805ba-136">In de grafiek worden standaard zowel de gegevens **phishing** als de **malware** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="805ba-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="805ba-137">Als u geen gegevens van een campagne ziet, probeer dan het datumbereik of de [filters](#filters-and-settings)te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="805ba-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="805ba-138">De rest van de pagina overzicht bevat de volgende informatie op het tabblad **campagne** :</span><span class="sxs-lookup"><span data-stu-id="805ba-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="805ba-139">**Naam**</span><span class="sxs-lookup"><span data-stu-id="805ba-139">**Name**</span></span>

- <span data-ttu-id="805ba-140">Voor **beeld van onderwerp**: het onderwerp van een van de berichten in de campagne.</span><span class="sxs-lookup"><span data-stu-id="805ba-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="805ba-141">Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.</span><span class="sxs-lookup"><span data-stu-id="805ba-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="805ba-142">**Targeted**: het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie)/(het totale aantal geadresseerden in de campagne voor alle organisaties in de service).</span><span class="sxs-lookup"><span data-stu-id="805ba-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="805ba-143">Met deze waarde wordt de mate aangegeven waarin de campagne specifiek wordt aangegeven voor uw organisatie (een hogere waarde), en die wordt doorgestuurd naar andere organisaties in de service (een lagere waarde).</span><span class="sxs-lookup"><span data-stu-id="805ba-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="805ba-144">**Type**: deze waarde is een **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="805ba-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="805ba-145">**Subtype**: deze waarde bevat meer details over de campagne.</span><span class="sxs-lookup"><span data-stu-id="805ba-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="805ba-146">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="805ba-146">For example:</span></span>

  - <span data-ttu-id="805ba-147">**Phishing**: indien beschikbaar, het merk dat wordt door deze campagne verphishd.</span><span class="sxs-lookup"><span data-stu-id="805ba-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="805ba-148">Bijvoorbeeld,, `Microsoft` , `365` `Unknown` `Outlook` of `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="805ba-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="805ba-149">**Malware**: bijvoorbeeld `HTML/PHISH` of `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="805ba-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="805ba-150">Indien beschikbaar, het merk dat door deze campagne wordt verphishd.</span><span class="sxs-lookup"><span data-stu-id="805ba-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="805ba-151">Wanneer de detectie wordt gestuurd met de ATP-technologie, wordt de **ATP-** voorvoegsel toegevoegd aan de waarde van het subtype.</span><span class="sxs-lookup"><span data-stu-id="805ba-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="805ba-152">**Geadresseerden**: het aantal gebruikers dat is gericht op deze campagne.</span><span class="sxs-lookup"><span data-stu-id="805ba-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="805ba-153">**Postvak in met postvak**in: het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun postvak in (niet bezorgd in de map Ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="805ba-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="805ba-154">**Geklikt**op: het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het malafide bericht heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="805ba-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="805ba-155">**Klik op rente**: het percentage zoals berekend door te**klikken**op  /  **Postvak in**.</span><span class="sxs-lookup"><span data-stu-id="805ba-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="805ba-156">Deze waarde is een indicator van de effectiviteit van de campagne, en of de geadresseerden het bericht als phishing konden identificeren en niet op de URL van de nettolading hoeven te klikken.</span><span class="sxs-lookup"><span data-stu-id="805ba-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="805ba-157">Houd er rekening mee dat deze waarde niet wordt gebruikt in malware van malware.</span><span class="sxs-lookup"><span data-stu-id="805ba-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="805ba-158">**Bezocht**: hoeveel gebruikers hebben dit via de website van uw nettolading gemaakt.</span><span class="sxs-lookup"><span data-stu-id="805ba-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="805ba-159">Als er op waarden werd **geklikt** , maar veilige koppelingen naar de website zijn geblokkeerd, is deze waarde nul.</span><span class="sxs-lookup"><span data-stu-id="805ba-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="805ba-160">Het tabblad **campagne oorsprong** bevat de berichten bronnen op een kaart van de wereld.</span><span class="sxs-lookup"><span data-stu-id="805ba-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="805ba-161">Filters en instellingen</span><span class="sxs-lookup"><span data-stu-id="805ba-161">Filters and settings</span></span>

<span data-ttu-id="805ba-162">Boven aan de pagina met campagne weergaven vindt u diverse filter-en queryinstellingen waarmee u specifieke campagnes kunt zoeken en isoleren.</span><span class="sxs-lookup"><span data-stu-id="805ba-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Campagne filters](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="805ba-164">De meest basisfilters die u kunt uitvoeren, zijn de begindatum/-tijd en de einddatum en-tijd.</span><span class="sxs-lookup"><span data-stu-id="805ba-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="805ba-165">Als u de weergave verder wilt filteren, kunt u één eigenschap met meerdere waarden filteren door te klikken op de knop **campagnetype** , uw selectie te maken en vervolgens op **vernieuwen**te klikken.</span><span class="sxs-lookup"><span data-stu-id="805ba-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="805ba-166">In de volgende lijst vindt u een beschrijving van de beschikbare campagne-eigenschappen:</span><span class="sxs-lookup"><span data-stu-id="805ba-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="805ba-167">Basis</span><span class="sxs-lookup"><span data-stu-id="805ba-167">Basic</span></span>

  - <span data-ttu-id="805ba-168">**Type campagne**: Selecteer **malware** of **phishing**.</span><span class="sxs-lookup"><span data-stu-id="805ba-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="805ba-169">Wanneer u de selecties uitschakelt, heeft dit hetzelfde resultaat als met beide.</span><span class="sxs-lookup"><span data-stu-id="805ba-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="805ba-170">**Naam van campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-170">**Campaign name**</span></span>
  - <span data-ttu-id="805ba-171">**Subtype campagne**</span><span class="sxs-lookup"><span data-stu-id="805ba-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="805ba-172">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="805ba-172">**Sender**</span></span>
  - <span data-ttu-id="805ba-173">**Allen**</span><span class="sxs-lookup"><span data-stu-id="805ba-173">**Recipients**</span></span>
  - <span data-ttu-id="805ba-174">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="805ba-174">**Sender domain**</span></span>
  - <span data-ttu-id="805ba-175">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="805ba-175">**Subject**</span></span>
  - <span data-ttu-id="805ba-176">**Bestandsnaam van bijlage**</span><span class="sxs-lookup"><span data-stu-id="805ba-176">**Attachment filename**</span></span>
  - <span data-ttu-id="805ba-177">**Familie van malware**</span><span class="sxs-lookup"><span data-stu-id="805ba-177">**Malware family**</span></span>
  - <span data-ttu-id="805ba-178">**Bezorgings actie**</span><span class="sxs-lookup"><span data-stu-id="805ba-178">**Delivery action**</span></span>
  - <span data-ttu-id="805ba-179">**Detectietechnologie**</span><span class="sxs-lookup"><span data-stu-id="805ba-179">**Detection technology**</span></span>
  - <span data-ttu-id="805ba-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="805ba-180">**Tags**</span></span>
  - <span data-ttu-id="805ba-181">**Systeem overschrijvingen**</span><span class="sxs-lookup"><span data-stu-id="805ba-181">**System overrides**</span></span>

- <span data-ttu-id="805ba-182">Geavanceerd</span><span class="sxs-lookup"><span data-stu-id="805ba-182">Advanced</span></span>

  - <span data-ttu-id="805ba-183">**Internet bericht-id**: beschikbaar in het veld **bericht-id-** koptekst in de kop van het bericht.</span><span class="sxs-lookup"><span data-stu-id="805ba-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="805ba-184">Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).</span><span class="sxs-lookup"><span data-stu-id="805ba-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="805ba-185">**Netwerkbericht-id**: een GUID-waarde die beschikbaar is in het veld **X-MS-Exchange-Organization-Network-Message-ID** in de kop van het bericht.</span><span class="sxs-lookup"><span data-stu-id="805ba-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="805ba-186">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="805ba-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="805ba-187">**Bijlage sha256**: als u de sha256-hashwaarde van een bestand wilt zoeken in Windows, voert u de volgende opdracht uit op een opdrachtregel: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="805ba-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="805ba-188">**Cluster-ID**</span><span class="sxs-lookup"><span data-stu-id="805ba-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="805ba-189">**ID van waarschuwings beleid**</span><span class="sxs-lookup"><span data-stu-id="805ba-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="805ba-190">URLs</span><span class="sxs-lookup"><span data-stu-id="805ba-190">URLs</span></span>

  - <span data-ttu-id="805ba-191">**URL-domein**</span><span class="sxs-lookup"><span data-stu-id="805ba-191">**URL domain**</span></span>
  - <span data-ttu-id="805ba-192">**URL Domain en Path**</span><span class="sxs-lookup"><span data-stu-id="805ba-192">**URL domain and path**</span></span>
  - <span data-ttu-id="805ba-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="805ba-193">**URL**</span></span>
  - <span data-ttu-id="805ba-194">**URL-pad**</span><span class="sxs-lookup"><span data-stu-id="805ba-194">**URL path**</span></span>
  - <span data-ttu-id="805ba-195">**Klik op Verdict**</span><span class="sxs-lookup"><span data-stu-id="805ba-195">**Click verdict**</span></span>

<span data-ttu-id="805ba-196">Voor uitgebreid filteren, waaronder filteren via meerdere eigenschappen, kunt u op de knop **Geavanceerd filter** klikken om een query te maken.</span><span class="sxs-lookup"><span data-stu-id="805ba-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="805ba-197">De eigenschappen van dezelfde campagne zijn beschikbaar, maar met de volgende verbeteringen:</span><span class="sxs-lookup"><span data-stu-id="805ba-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="805ba-198">U kunt op **een voorwaarde toevoegen** klikken om meerdere voorwaarden te selecteren.</span><span class="sxs-lookup"><span data-stu-id="805ba-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="805ba-199">U kunt de operator **and** of **or** kiezen tussen voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="805ba-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="805ba-200">U kunt het item **voor de voorwaarde-groep** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.</span><span class="sxs-lookup"><span data-stu-id="805ba-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="805ba-201">Wanneer u klaar bent, klikt u op de knop **query** .</span><span class="sxs-lookup"><span data-stu-id="805ba-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="805ba-202">Nadat u een basis-of Geavanceerd filter hebt gemaakt, kunt u dit opslaan met behulp van **query opslaan** of **query opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="805ba-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="805ba-203">Wanneer u later terugkeert naar de weergave campagne, kunt u een opgeslagen filter laden door te klikken op **opgeslagen queryinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="805ba-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="805ba-204">Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **exporteren** en selecteert u **grafiekgegevens exporteren** of **campagnelijst exporteren**.</span><span class="sxs-lookup"><span data-stu-id="805ba-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="805ba-205">Als u een abonnement op Microsoft Defender ATP hebt, kunt u op **WDATP** klikken om verbinding te maken met de gegevens van de campagnes of de gegevens ervan te verbreken met Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="805ba-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="805ba-206">Zie voor meer informatie [Office 365-ATP integreren met Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="805ba-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="805ba-207">Campagne Details</span><span class="sxs-lookup"><span data-stu-id="805ba-207">Campaign details</span></span>

<span data-ttu-id="805ba-208">Wanneer u op de naam van een campagne klikt, worden de gegevens van de campagne in een flyout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="805ba-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="805ba-209">Campagne-informatie</span><span class="sxs-lookup"><span data-stu-id="805ba-209">Campaign information</span></span>

<span data-ttu-id="805ba-210">Boven in de weergave met campagnegegevens zijn de volgende gegevens van de campagne beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="805ba-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="805ba-211">**Id**: de unieke campagne-id.</span><span class="sxs-lookup"><span data-stu-id="805ba-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="805ba-212">**Begonnen** en **beëindigd**: de begindatum en einddatum van de campagne.</span><span class="sxs-lookup"><span data-stu-id="805ba-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="805ba-213">Houd er rekening mee dat deze datums mogelijk verder lopen dan de filter datums die u hebt geselecteerd op de pagina overzicht.</span><span class="sxs-lookup"><span data-stu-id="805ba-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="805ba-214">**Impact**: deze sectie bevat de volgende gegevens voor het datumbereik dat u hebt geselecteerd (of die u in de tijdlijn selecteert):</span><span class="sxs-lookup"><span data-stu-id="805ba-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="805ba-215">Het totale aantal geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="805ba-215">The total number of recipients.</span></span>
  - <span data-ttu-id="805ba-216">Het aantal berichten dat is verzonden naar het postvak in (dat wordt bezorgd in het postvak in, niet op de map Ongewenste E-mail).</span><span class="sxs-lookup"><span data-stu-id="805ba-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="805ba-217">Hoeveel gebruikers klikken op de URL-nettolading in het malafide bericht.</span><span class="sxs-lookup"><span data-stu-id="805ba-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="805ba-218">Howe veel gebruikers hebben de URL bezocht.</span><span class="sxs-lookup"><span data-stu-id="805ba-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="805ba-219">**Targeted**: het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie)/(het totale aantal geadresseerden in de campagne voor alle organisaties in de service).</span><span class="sxs-lookup"><span data-stu-id="805ba-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="805ba-220">Houd er rekening mee dat deze waarde wordt berekend gedurende de hele levensduur van de campagne, en geen invloed heeft op de filter datums.</span><span class="sxs-lookup"><span data-stu-id="805ba-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="805ba-221">Een interactieve tijdlijn van een campagneactiviteit: de tijdlijn toont de activiteiten gedurende de hele levensduur van de campagne.</span><span class="sxs-lookup"><span data-stu-id="805ba-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="805ba-222">Het gearceerd gebied bevat standaard het datumbereik filter dat u hebt geselecteerd in het overzicht.</span><span class="sxs-lookup"><span data-stu-id="805ba-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="805ba-223">U kunt klikken en slepen om een specifiek beginpunt en eindpunt te selecteren, <u>waardoor de gegevens die worden weergegeven in het gebied met **impact** en op de rest van de pagina, zoals beschreven in de volgende secties, worden gewijzigd</u>.</span><span class="sxs-lookup"><span data-stu-id="805ba-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="805ba-224">U kunt op de titelbalk op de knop **campagne-afschrijven downloaden** ![ campagne klikken ](../../media/download-campaign-write-up-button.png) om de campagne details te downloaden naar een Word-document (standaard met de naam CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="805ba-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="805ba-225">Dit document bevat details over de volledige levensduur van de campagne (niet alleen de filter datums die u hebt geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="805ba-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Campagne-informatie](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="805ba-227">Campagne stroom</span><span class="sxs-lookup"><span data-stu-id="805ba-227">Campaign flow</span></span>

<span data-ttu-id="805ba-228">In het midden van de weergave met campagne Details worden belangrijke informatie over de campagne weergegeven in de sectie **stroom** in een horizontaal-stroomdiagram (genaamd een _Sankey_ -diagram).</span><span class="sxs-lookup"><span data-stu-id="805ba-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="805ba-229">Met deze informatie kunt u inzicht krijgen in de elementen van de campagne en de potentiële impact van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="805ba-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="805ba-230">De informatie die in het **stroom** diagram wordt weergegeven, wordt bepaald door het gearceerde datumbereik in de tijdlijn zoals beschreven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="805ba-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Campagne details die geen gebruikers-URL klikken](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="805ba-232">Als u de muisaanwijzer over een horizontale band in het diagram houdt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaalde bron-IP, berichten van het bron-IP-adres met het opgegeven afzender domein, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="805ba-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="805ba-233">Het diagram bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="805ba-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="805ba-234">**Ip's van afzender**</span><span class="sxs-lookup"><span data-stu-id="805ba-234">**Sender IPs**</span></span>

- <span data-ttu-id="805ba-235">**Zender domeinen**</span><span class="sxs-lookup"><span data-stu-id="805ba-235">**Sender domains**</span></span>

- <span data-ttu-id="805ba-236">**Filter Verdicts**: deze waarden zijn gerelateerd aan de beschikbare Verdicts voor phishing en spam filteren, zoals wordt beschreven in [anti spambericht koppen](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="805ba-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="805ba-237">In de volgende tabel vindt u een beschrijving van de beschikbare waarden:</span><span class="sxs-lookup"><span data-stu-id="805ba-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="805ba-238">Value</span><span class="sxs-lookup"><span data-stu-id="805ba-238">Value</span></span>|<span data-ttu-id="805ba-239">Spam filter verdict</span><span class="sxs-lookup"><span data-stu-id="805ba-239">Spam filter verdict</span></span>|<span data-ttu-id="805ba-240">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="805ba-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="805ba-241">**Ingesteld**</span><span class="sxs-lookup"><span data-stu-id="805ba-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="805ba-242">Het bericht is gemarkeerd als niet-spam en/of overgeslagen filters voordat het wordt geëvalueerd door spam te filteren (bijvoorbeeld met een e-mail stroom regel, ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="805ba-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="805ba-243">Het bericht heeft geen spam gefilterd op andere redenen (de afzender en de geadresseerde lijken in dezelfde organisatie).</span><span class="sxs-lookup"><span data-stu-id="805ba-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="805ba-244">**Blokkeert**</span><span class="sxs-lookup"><span data-stu-id="805ba-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="805ba-245">Het bericht is gemarkeerd als spam voordat ze worden geëvalueerd via spamfilters (bijvoorbeeld via een e-mail stroom regel).</span><span class="sxs-lookup"><span data-stu-id="805ba-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="805ba-246">**Aangetoond**</span><span class="sxs-lookup"><span data-stu-id="805ba-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="805ba-247">Het bericht is gemarkeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="805ba-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="805ba-248">**Niet gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="805ba-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="805ba-249">Het bericht is gemarkeerd als geen spam via spamfilters.</span><span class="sxs-lookup"><span data-stu-id="805ba-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="805ba-250">**Uitgebracht**</span><span class="sxs-lookup"><span data-stu-id="805ba-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="805ba-251">Het bericht heeft het filteren van spam genegeerd, omdat het is vrijgegeven uit Quarantine.</span><span class="sxs-lookup"><span data-stu-id="805ba-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="805ba-252">**Tenant toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="805ba-253">Het bericht is overgeslagen op spam filteren vanwege antispam beleidsinstellingen (de afzender bevonden zich bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinen).</span><span class="sxs-lookup"><span data-stu-id="805ba-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="805ba-254">**Tenant blok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="805ba-255">Het bericht is geblokkeerd door spam te filteren vanwege antispam beleidsinstellingen (de afzender stond in de lijst met toegestane afzenders of toegestane domeinen).</span><span class="sxs-lookup"><span data-stu-id="805ba-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="805ba-256">**Gebruiker toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="805ba-257">Het bericht is overgeslagen op spam filteren omdat de afzender in de lijst met veilige afzenders van een gebruiker in Outlook.</span><span class="sxs-lookup"><span data-stu-id="805ba-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="805ba-258">**Gebruikers blok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="805ba-259">Het bericht is geblokkeerd door spam te filteren omdat de afzender in de lijst met geblokkeerde afzenders van een gebruiker in Outlook was.</span><span class="sxs-lookup"><span data-stu-id="805ba-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="805ba-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="805ba-260">**ZAP**</span></span>|<span data-ttu-id="805ba-261">n/b</span><span class="sxs-lookup"><span data-stu-id="805ba-261">n/a</span></span>|<span data-ttu-id="805ba-262">[Zero-Hour auto leegmaak actie (ZAP)](zero-hour-auto-purge.md) heeft de actie uitgevoerd op het bezorgde bericht overeenkomstig de instellingen van uw Antispambeleid (verplaatst naar de map Ongewenste e-mail of in quarantaine).</span><span class="sxs-lookup"><span data-stu-id="805ba-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="805ba-263"><sup>\*</sup> Controleer uw Antispambeleid, omdat het toegestane bericht waarschijnlijk door de dienst werd geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="805ba-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="805ba-264"><sup>\*\*</sup> Controleer uw Antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="805ba-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="805ba-265">**Bezorgingslocaties**: u wilt waarschijnlijk berichten onderzoeken die daadwerkelijk voor geadresseerden zijn afgeleverd (naar het postvak in of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de nettolading in het bericht klikken.</span><span class="sxs-lookup"><span data-stu-id="805ba-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="805ba-266">U kunt ook de in quarantaine geplaatste berichten verwijderen uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="805ba-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="805ba-267">Zie voor meer informatie [Gequarantinee e-mailberichten in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="805ba-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="805ba-268">**Map verwijderd**</span><span class="sxs-lookup"><span data-stu-id="805ba-268">**Deleted folder**</span></span>
  - <span data-ttu-id="805ba-269">**Drop**</span><span class="sxs-lookup"><span data-stu-id="805ba-269">**Dropped**</span></span>
  - <span data-ttu-id="805ba-270">**Extern**: de geadresseerde bevindt zich in de on-premises e-mail organisatie in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="805ba-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="805ba-271">**Mislukt**</span><span class="sxs-lookup"><span data-stu-id="805ba-271">**Failed**</span></span>
  - <span data-ttu-id="805ba-272">**Ter**</span><span class="sxs-lookup"><span data-stu-id="805ba-272">**Forwarded**</span></span>
  - <span data-ttu-id="805ba-273">**Postvak in**</span><span class="sxs-lookup"><span data-stu-id="805ba-273">**Inbox**</span></span>
  - <span data-ttu-id="805ba-274">**Map Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="805ba-274">**Junk folder**</span></span>
  - <span data-ttu-id="805ba-275">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="805ba-275">**Quarantine**</span></span>
  - <span data-ttu-id="805ba-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="805ba-276">**Unknown**</span></span>

- <span data-ttu-id="805ba-277">**URL-klikken**: deze worden beschreven in het volgende gedeelte.</span><span class="sxs-lookup"><span data-stu-id="805ba-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="805ba-278">Op alle lagen met meer dan 10 items worden de bovenste 10 items weergegeven, terwijl de rest in de **andere**lagen bijeen.</span><span class="sxs-lookup"><span data-stu-id="805ba-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="805ba-279">URL'S klikken</span><span class="sxs-lookup"><span data-stu-id="805ba-279">URL clicks</span></span>

<span data-ttu-id="805ba-280">Wanneer een malafide bericht wordt afgeleverd bij een geadresseerde (het postvak in of de map Ongewenste E-mail), is er altijd een kans dat de gebruiker op de URL van de nettolading klikt.</span><span class="sxs-lookup"><span data-stu-id="805ba-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="805ba-281">U kunt niet op de URL in een geleverd bericht klikken, maar u moet op de eerste plaats bepalen waarom het malafide bericht is bezorgd bij hun postvak.</span><span class="sxs-lookup"><span data-stu-id="805ba-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="805ba-282">Als een gebruiker in het malafide e-mailbericht op de URL van de nettolading heeft geklikt, worden de acties weergegeven in het gebied voor de **URL-klikken** van het diagram in de weergave campagne Details.</span><span class="sxs-lookup"><span data-stu-id="805ba-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="805ba-283">**Ingesteld**</span><span class="sxs-lookup"><span data-stu-id="805ba-283">**Allowed**</span></span>

- <span data-ttu-id="805ba-284">**BlockPage**: de geadresseerde heeft op de URL van de nettolading geklikt, maar de toegang tot de schadelijke website werd geblokkeerd door het beleid voor [veilige koppelingen](atp-safe-links.md) in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="805ba-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="805ba-285">**BlockPageOverride**: de geadresseerde die in het bericht op de URL van de nettolading hebt geklikt, heeft getrachte ATP-koppelingen geprobeerd ze te stoppen, maar ze kunnen het blok negeren.</span><span class="sxs-lookup"><span data-stu-id="805ba-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="805ba-286">U moet uw beleid voor [veilige koppelingen](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers de verdict voor veilige koppelingen mogen negeren en doorgaan naar de schadelijke website.</span><span class="sxs-lookup"><span data-stu-id="805ba-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="805ba-287">**PendingDetonationPage**: veilige bijlagen voor ATP wordt geopend met het openen van de URL van de nettolading in een virtuele computeromgeving, zodat u kunt zien wat er gebeurt.</span><span class="sxs-lookup"><span data-stu-id="805ba-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="805ba-288">**PendingDetonationPageOverride**: de geadresseerde mag de detonatie procedure overschrijven en de URL openen zonder te hoeven wachten tot de resultaten.</span><span class="sxs-lookup"><span data-stu-id="805ba-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="805ba-289">Tabvolgorde</span><span class="sxs-lookup"><span data-stu-id="805ba-289">Tabs</span></span>

<span data-ttu-id="805ba-290">Op de tabbladen in de weergave campagne Details kunt u de campagne verder onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="805ba-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="805ba-291">De informatie die wordt weergegeven op de tabbladen, wordt bepaald door het gearceerde datumbereik op de tijdlijn, zoals beschreven in de sectie [campagnegegevens](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="805ba-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="805ba-292">**URL-klikken**: als gebruikers niet op de URL van de nettolading in het phishingberichten klikken, is dit gedeelte leeg.</span><span class="sxs-lookup"><span data-stu-id="805ba-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="805ba-293">Als een gebruiker op de URL kon klikken, worden de volgende waarden ingevuld:</span><span class="sxs-lookup"><span data-stu-id="805ba-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="805ba-294">**Aanmeldings**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="805ba-295">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="805ba-296">**Klik op tijd**</span><span class="sxs-lookup"><span data-stu-id="805ba-296">**Click time**</span></span>
  - <span data-ttu-id="805ba-297">**Klik op Verdict**</span><span class="sxs-lookup"><span data-stu-id="805ba-297">**Click verdict**</span></span>

- <span data-ttu-id="805ba-298">**Ip's van afzender**</span><span class="sxs-lookup"><span data-stu-id="805ba-298">**Sender IPs**</span></span>

  - <span data-ttu-id="805ba-299">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="805ba-300">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="805ba-300">**Total count**</span></span>
  - <span data-ttu-id="805ba-301">**Postvak in**</span><span class="sxs-lookup"><span data-stu-id="805ba-301">**Inboxed**</span></span>
  - <span data-ttu-id="805ba-302">**Niet in Postvak in**</span><span class="sxs-lookup"><span data-stu-id="805ba-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="805ba-303">**SPF doorgegeven**: de afzender is geauthenticeerd door het [beleidsraamwerk voor verzenders (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="805ba-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="805ba-304">Een afzender die SPF valideert, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.</span><span class="sxs-lookup"><span data-stu-id="805ba-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="805ba-305">**Afzenders**</span><span class="sxs-lookup"><span data-stu-id="805ba-305">**Senders**</span></span>

  - <span data-ttu-id="805ba-306">**Afzender**: dit is het werkelijke adres van de afzender in de SMTP-e-mail van de opdracht, wat niet het is: een e-mailadres dat gebruikers zien in hun e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="805ba-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="805ba-307">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="805ba-307">**Total count**</span></span>
  - <span data-ttu-id="805ba-308">**Postvak in**</span><span class="sxs-lookup"><span data-stu-id="805ba-308">**Inboxed**</span></span>
  - <span data-ttu-id="805ba-309">**Niet in Postvak in**</span><span class="sxs-lookup"><span data-stu-id="805ba-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="805ba-310">**Dkim doorgegeven**: de afzender is geverifieerd door de [domein sleutels, die e-mail (dkim) heeft geïdentificeerd](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="805ba-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="805ba-311">Een afzender die geen DKIM-validatie geeft, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.</span><span class="sxs-lookup"><span data-stu-id="805ba-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="805ba-312">**DMARC doorgegeven**: de afzender is geverifieerd door [verificatie op basis van een domein op basis van een berichtverificatie, rapportering en conformiteit (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="805ba-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="805ba-313">Een afzender die geen DMARC-validatie geeft, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.</span><span class="sxs-lookup"><span data-stu-id="805ba-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="805ba-314">**Stukken**</span><span class="sxs-lookup"><span data-stu-id="805ba-314">**Attachments**</span></span>

  - <span data-ttu-id="805ba-315">**Namen**</span><span class="sxs-lookup"><span data-stu-id="805ba-315">**Filename**</span></span>
  - <span data-ttu-id="805ba-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="805ba-316">**SHA256**</span></span>
  - <span data-ttu-id="805ba-317">**Familie van malware**</span><span class="sxs-lookup"><span data-stu-id="805ba-317">**Malware family**</span></span>
  - <span data-ttu-id="805ba-318">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="805ba-318">**Total count**</span></span>

- <span data-ttu-id="805ba-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="805ba-319">**URL**</span></span>

  - <span data-ttu-id="805ba-320">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="805ba-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="805ba-321">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="805ba-321">**Total Count**</span></span>

<span data-ttu-id="805ba-322"><sup>\*</sup> Als u op deze waarde klikt, wordt een nieuwe flyout geopend met meer informatie over het opgegeven item (gebruiker, URL, etc.) boven aan de weergave campagne Details.</span><span class="sxs-lookup"><span data-stu-id="805ba-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="805ba-323">Als u wilt teruggaan naar de weergave met campagnegegevens, klikt u op **gereed** in de vervolgmenu nieuw.</span><span class="sxs-lookup"><span data-stu-id="805ba-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="805ba-324">Hardwareknoppen</span><span class="sxs-lookup"><span data-stu-id="805ba-324">Buttons</span></span>

<span data-ttu-id="805ba-325">Met de knoppen in de weergave campagne Details kunt u de kracht van de bedreigings Verkenner gebruiken om de campagne verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="805ba-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="805ba-326">**Campagne verkennen**: Hiermee opent u een nieuw tabblad Zoeken in de bedreiging van een nieuwe bedreiging met de waarde van de **campagne-id** als het zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="805ba-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="805ba-327">**Berichten in Postvak in verkennen**: Hiermee opent u een nieuw Zoek tabblad van de bedreigings Verkenner met behulp van de **campagne-id** en locatie van de **geadresseerde: Postvak in** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="805ba-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
