---
title: Campagneweergaven in ATP
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039451"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="eb224-103">Campagneweergaven in ATP</span><span class="sxs-lookup"><span data-stu-id="eb224-103">Campaign Views in ATP</span></span>

<span data-ttu-id="eb224-104">Campaign Views is een functie in Advanced Threat Protection (ATP) in het Security & Compliance Center dat phishing-aanvallen in de service identificeert en categoriseert.</span><span class="sxs-lookup"><span data-stu-id="eb224-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="eb224-105">Campagneweergaven kunnen u helpen om:</span><span class="sxs-lookup"><span data-stu-id="eb224-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="eb224-106">Onderzoek en reageer efficiënt op phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="eb224-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="eb224-107">Beter begrijpen van de omvang van de aanval.</span><span class="sxs-lookup"><span data-stu-id="eb224-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="eb224-108">Toon waarde aan besluitvormers.</span><span class="sxs-lookup"><span data-stu-id="eb224-108">Show value to decision makers.</span></span>

<span data-ttu-id="eb224-109">Met campagneweergaven kun je het grote plaatje van een aanval sneller en completer zien dan welke mens dan ook.</span><span class="sxs-lookup"><span data-stu-id="eb224-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="eb224-110">Wat is een campagne?</span><span class="sxs-lookup"><span data-stu-id="eb224-110">What is a campaign?</span></span>

<span data-ttu-id="eb224-111">Een campagne is een gecoördineerde e-mailaanval tegen een of meer organisaties.</span><span class="sxs-lookup"><span data-stu-id="eb224-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="eb224-112">E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie.</span><span class="sxs-lookup"><span data-stu-id="eb224-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="eb224-113">Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om blijvend succes te garanderen.</span><span class="sxs-lookup"><span data-stu-id="eb224-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="eb224-114">Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing, anti-spam en anti-malware gegevens in de hele service om te helpen bij het identificeren van campagnes.</span><span class="sxs-lookup"><span data-stu-id="eb224-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="eb224-115">We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren.</span><span class="sxs-lookup"><span data-stu-id="eb224-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="eb224-116">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="eb224-116">For example:</span></span>

- <span data-ttu-id="eb224-117">**Aanvalsbron**: De bron-IP-adressen en e-maildomeinen van afzenders.</span><span class="sxs-lookup"><span data-stu-id="eb224-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="eb224-118">**Eigenschappen van het bericht aan te vallen:** de inhoud, stijl en toon van de berichten.</span><span class="sxs-lookup"><span data-stu-id="eb224-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="eb224-119">**Ontvangers van aanvallen**: geadresseerdedomeinen, geadresseerde functiefuncties (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privé, enz.) en bedrijfstakken.</span><span class="sxs-lookup"><span data-stu-id="eb224-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="eb224-120">**Aanval payload:** Kwaadaardige links, bijlagen, of andere payloads in de berichten.</span><span class="sxs-lookup"><span data-stu-id="eb224-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="eb224-121">Een campagne kan van korte duur zijn, of kan meerdere dagen, weken of maanden met actieve en inactieve perioden omvatten.</span><span class="sxs-lookup"><span data-stu-id="eb224-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="eb224-122">Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eb224-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="eb224-123">Campagne bekijkt het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="eb224-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="eb224-124">Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **management** \> **Campaigns**, of rechtstreeks op <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="eb224-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Overzicht van campagnes in het Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="eb224-126">Je ook campagneweergaven bekijken via:</span><span class="sxs-lookup"><span data-stu-id="eb224-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="eb224-127">**Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Campagnes**</span><span class="sxs-lookup"><span data-stu-id="eb224-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="eb224-128">**Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Alle e-mail** \> **Tabblad Campagne**</span><span class="sxs-lookup"><span data-stu-id="eb224-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="eb224-129">**Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Phish Phish** \> **Tabblad Campagne**</span><span class="sxs-lookup"><span data-stu-id="eb224-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="eb224-130">**Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Malware** \> **Tabblad Campagne**</span><span class="sxs-lookup"><span data-stu-id="eb224-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="eb224-131">Als u toegang wilt krijgen tot campagneweergaven, moet u lid zijn van de rolgroepen **Organisatiebeheer,** **Beveiligingsbeheerder**of **Beveiligingslezer** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="eb224-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="eb224-132">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb224-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="eb224-133">Overzicht van campagnes</span><span class="sxs-lookup"><span data-stu-id="eb224-133">Campaigns overview</span></span>

<span data-ttu-id="eb224-134">Op de overzichtspagina vindt u informatie over alle campagnes.</span><span class="sxs-lookup"><span data-stu-id="eb224-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="eb224-135">Op het **tabblad** Campagne toont het gebied **Campagnetype** een staafgrafiek met het aantal geadresseerden per dag.</span><span class="sxs-lookup"><span data-stu-id="eb224-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="eb224-136">Standaard toont de grafiek zowel **Phish-** als **malwaregegevens.**</span><span class="sxs-lookup"><span data-stu-id="eb224-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="eb224-137">Als u geen campagnegegevens ziet, probeert u het datumbereik of de [filters](#filters-and-settings)te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="eb224-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="eb224-138">De rest van de overzichtspagina bevat de volgende informatie op het tabblad **Campagne:**</span><span class="sxs-lookup"><span data-stu-id="eb224-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="eb224-139">**Naam**</span><span class="sxs-lookup"><span data-stu-id="eb224-139">**Name**</span></span>

- <span data-ttu-id="eb224-140">**Voorbeeldonderwerp**: De onderwerpregel van een van de berichten in de campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="eb224-141">Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.</span><span class="sxs-lookup"><span data-stu-id="eb224-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="eb224-142">**Doel:** het percentage zoals berekend door: (het aantal campagneontvangers in uw organisatie) / (het totale aantal ontvangers in de campagne voor alle organisaties in de service).</span><span class="sxs-lookup"><span data-stu-id="eb224-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="eb224-143">Deze waarde geeft de mate aan waarin de campagne specifiek is gericht op uw organisatie (een hogere waarde) versus gericht op andere organisaties in de service (een lagere waarde).</span><span class="sxs-lookup"><span data-stu-id="eb224-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="eb224-144">**Type**: Deze waarde is **Phish** of **Malware**.</span><span class="sxs-lookup"><span data-stu-id="eb224-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="eb224-145">**Subtype**: Deze waarde bevat meer details over de campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="eb224-146">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="eb224-146">For example:</span></span>

  - <span data-ttu-id="eb224-147">**Phish**: Waar beschikbaar, het merk dat wordt geprofraakt door deze campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="eb224-148">Bijvoorbeeld `Microsoft` , `365` , , , `Unknown` of `Outlook` `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="eb224-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="eb224-149">**Malware**: Bijvoorbeeld, `HTML/PHISH` of `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="eb224-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="eb224-150">Waar beschikbaar, het merk dat wordt geprofraseerd door deze campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="eb224-151">Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.</span><span class="sxs-lookup"><span data-stu-id="eb224-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="eb224-152">**Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="eb224-153">**Inbox:** het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan hun map Ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="eb224-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="eb224-154">**Geklikt**: het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het phishingbericht heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="eb224-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="eb224-155">**Klikfrequentie**: Het percentage zoals berekend door "**Geklikt**  /  **Postvak IN**".</span><span class="sxs-lookup"><span data-stu-id="eb224-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="eb224-156">Deze waarde is een indicator van de effectiviteit van de campagne en of de ontvangers het bericht als phishing hebben kunnen identificeren en te voorkomen dat ze op de URL van de payload klikken.</span><span class="sxs-lookup"><span data-stu-id="eb224-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="eb224-157">Houd er rekening mee dat deze waarde niet wordt gebruikt in malwarecampagnes.</span><span class="sxs-lookup"><span data-stu-id="eb224-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="eb224-158">**Bezocht :** Hoeveel gebruikers eigenlijk maakte het door naar de payload website.</span><span class="sxs-lookup"><span data-stu-id="eb224-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="eb224-159">Als er **geklikte** waarden zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.</span><span class="sxs-lookup"><span data-stu-id="eb224-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="eb224-160">Het tabblad **Campagneoorsprong** toont de berichtbronnen op een kaart van de wereld.</span><span class="sxs-lookup"><span data-stu-id="eb224-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="eb224-161">Filters en instellingen</span><span class="sxs-lookup"><span data-stu-id="eb224-161">Filters and settings</span></span>

<span data-ttu-id="eb224-162">Boven aan de pagina Campagneweergaven staan verschillende filter- en query-instellingen om u te helpen specifieke campagnes te vinden en te isoleren.</span><span class="sxs-lookup"><span data-stu-id="eb224-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Campagnefilters](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="eb224-164">De meest elementaire filtering die u doen is de begindatum/tijd en de einddatum/tijd.</span><span class="sxs-lookup"><span data-stu-id="eb224-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="eb224-165">Als u de weergave verder wilt filteren, u één eigenschap met meerdere waarden filteren door op de knop **Campagnetype** te klikken, uw selectie te maken en vervolgens op **Vernieuwen**te klikken.</span><span class="sxs-lookup"><span data-stu-id="eb224-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="eb224-166">De beschikbare campagne-eigenschappen worden beschreven in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="eb224-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="eb224-167">Basic</span><span class="sxs-lookup"><span data-stu-id="eb224-167">Basic</span></span>

  - <span data-ttu-id="eb224-168">**Campagnetype**: Selecteer **malware** of **Phish**.</span><span class="sxs-lookup"><span data-stu-id="eb224-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="eb224-169">Het wissen van de selecties heeft hetzelfde resultaat als het selecteren van beide.</span><span class="sxs-lookup"><span data-stu-id="eb224-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="eb224-170">**Campagnenaam**</span><span class="sxs-lookup"><span data-stu-id="eb224-170">**Campaign name**</span></span>
  - <span data-ttu-id="eb224-171">**Campagne subtype**</span><span class="sxs-lookup"><span data-stu-id="eb224-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="eb224-172">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="eb224-172">**Sender**</span></span>
  - <span data-ttu-id="eb224-173">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="eb224-173">**Recipients**</span></span>
  - <span data-ttu-id="eb224-174">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="eb224-174">**Sender domain**</span></span>
  - <span data-ttu-id="eb224-175">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="eb224-175">**Subject**</span></span>
  - <span data-ttu-id="eb224-176">**Bestandsnaam voor bijlagen**</span><span class="sxs-lookup"><span data-stu-id="eb224-176">**Attachment filename**</span></span>
  - <span data-ttu-id="eb224-177">**Malware familie**</span><span class="sxs-lookup"><span data-stu-id="eb224-177">**Malware family**</span></span>
  - <span data-ttu-id="eb224-178">**Leveringsactie**</span><span class="sxs-lookup"><span data-stu-id="eb224-178">**Delivery action**</span></span>
  - <span data-ttu-id="eb224-179">**Detectietechnologie**</span><span class="sxs-lookup"><span data-stu-id="eb224-179">**Detection technology**</span></span>
  - <span data-ttu-id="eb224-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="eb224-180">**Tags**</span></span>
  - <span data-ttu-id="eb224-181">**Systeemoverschrijvingen**</span><span class="sxs-lookup"><span data-stu-id="eb224-181">**System overrides**</span></span>

- <span data-ttu-id="eb224-182">Geavanceerde</span><span class="sxs-lookup"><span data-stu-id="eb224-182">Advanced</span></span>

  - <span data-ttu-id="eb224-183">**Internetbericht-id**: beschikbaar in het kopveld **Bericht-ID** in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="eb224-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="eb224-184">Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaakjes).</span><span class="sxs-lookup"><span data-stu-id="eb224-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="eb224-185">**Netwerkbericht-ID:** een GUID-waarde die beschikbaar is in het kopveld **X-MS-Exchange-Organization-Network-Message-Id** in de berichtkop.</span><span class="sxs-lookup"><span data-stu-id="eb224-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="eb224-186">**IP-adres van afzender**</span><span class="sxs-lookup"><span data-stu-id="eb224-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="eb224-187">**Bijlage SHA256**: Als u de SHA256-hashwaarde van een bestand in Windows wilt zoeken, voert u de volgende opdracht uit in een opdrachtprompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="eb224-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="eb224-188">**Cluster-id**</span><span class="sxs-lookup"><span data-stu-id="eb224-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="eb224-189">**Waarschuwingsbeleids-id**</span><span class="sxs-lookup"><span data-stu-id="eb224-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="eb224-190">Urls</span><span class="sxs-lookup"><span data-stu-id="eb224-190">URLs</span></span>

  - <span data-ttu-id="eb224-191">**URL-domein**</span><span class="sxs-lookup"><span data-stu-id="eb224-191">**URL domain**</span></span>
  - <span data-ttu-id="eb224-192">**URL-domein en -pad**</span><span class="sxs-lookup"><span data-stu-id="eb224-192">**URL domain and path**</span></span>
  - <span data-ttu-id="eb224-193">**Url**</span><span class="sxs-lookup"><span data-stu-id="eb224-193">**URL**</span></span>
  - <span data-ttu-id="eb224-194">**URL-pad**</span><span class="sxs-lookup"><span data-stu-id="eb224-194">**URL path**</span></span>
  - <span data-ttu-id="eb224-195">**Klik op vonnis**</span><span class="sxs-lookup"><span data-stu-id="eb224-195">**Click verdict**</span></span>

<span data-ttu-id="eb224-196">Voor meer geavanceerde filtering, inclusief filtering op meerdere eigenschappen, u op de **knop Geavanceerd filter** klikken om een query te maken.</span><span class="sxs-lookup"><span data-stu-id="eb224-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="eb224-197">Dezelfde campagne-eigenschappen zijn beschikbaar, maar met de volgende verbeteringen:</span><span class="sxs-lookup"><span data-stu-id="eb224-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="eb224-198">U op **Een voorwaarde toevoegen** klikken om meerdere voorwaarden te selecteren.</span><span class="sxs-lookup"><span data-stu-id="eb224-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="eb224-199">U de **operator And** or **Or** kiezen tussen de voorwaarden.</span><span class="sxs-lookup"><span data-stu-id="eb224-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="eb224-200">U het item **Voorwaardegroep** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.</span><span class="sxs-lookup"><span data-stu-id="eb224-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="eb224-201">Als u klaar bent, klikt u op de knop **Query.**</span><span class="sxs-lookup"><span data-stu-id="eb224-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="eb224-202">Nadat u een basis- of geavanceerd filter hebt gemaakt, u het opslaan door **query opslaan** of Query **opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="eb224-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="eb224-203">Wanneer u later terugkeert naar campagneweergaven, u een opgeslagen filter laden door op **opgeslagen query-instellingen**te klikken.</span><span class="sxs-lookup"><span data-stu-id="eb224-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="eb224-204">Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **Exporteren** en selecteert u **Grafiekgegevens exporteren** of **campagnelijst exporteren**.</span><span class="sxs-lookup"><span data-stu-id="eb224-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="eb224-205">Als u een Microsoft Defender ATP-abonnement hebt, u op **WDATP** klikken om de campagnegegevens te koppelen of los te koppelen met Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="eb224-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="eb224-206">Zie [Office 365 ATP integreren met Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb224-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="eb224-207">Campagnegegevens</span><span class="sxs-lookup"><span data-stu-id="eb224-207">Campaign details</span></span>

<span data-ttu-id="eb224-208">Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="eb224-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="eb224-209">Campagne-informatie</span><span class="sxs-lookup"><span data-stu-id="eb224-209">Campaign information</span></span>

<span data-ttu-id="eb224-210">Boven aan de campagnedetailsweergave is de volgende campagne-informatie beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="eb224-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="eb224-211">**ID**: De unieke campagne-id.</span><span class="sxs-lookup"><span data-stu-id="eb224-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="eb224-212">**Gestart** en **beëindigd:** de begin- en einddatum van de campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="eb224-213">Houd er rekening mee dat deze datums verder kunnen reiken dan uw filterdatums die u hebt geselecteerd op de overzichtspagina.</span><span class="sxs-lookup"><span data-stu-id="eb224-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="eb224-214">**Impact**: deze sectie bevat de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd (of dat u selecteert in de tijdlijn):</span><span class="sxs-lookup"><span data-stu-id="eb224-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="eb224-215">Het totale aantal ontvangers.</span><span class="sxs-lookup"><span data-stu-id="eb224-215">The total number of recipients.</span></span>
  - <span data-ttu-id="eb224-216">Het aantal berichten dat inbox was (dat wil zeggen, geleverd aan het Postvak IN, niet naar de map Ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="eb224-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="eb224-217">Hoeveel gebruikers klikten op de URL payload in het phishing-bericht.</span><span class="sxs-lookup"><span data-stu-id="eb224-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="eb224-218">Hoeveel gebruikers hebben de URL bezocht.</span><span class="sxs-lookup"><span data-stu-id="eb224-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="eb224-219">**Doel:** het percentage zoals berekend door: (het aantal campagneontvangers in uw organisatie) / (het totale aantal ontvangers in de campagne voor alle organisaties in de service).</span><span class="sxs-lookup"><span data-stu-id="eb224-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="eb224-220">Houd er rekening mee dat deze waarde wordt berekend over de gehele levensduur van de campagne en dat de filterdatums niet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eb224-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="eb224-221">Een interactieve tijdlijn van campagneactiviteit: de tijdlijn toont activiteit gedurende de gehele levensduur van de campagne.</span><span class="sxs-lookup"><span data-stu-id="eb224-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="eb224-222">Standaard bevat het gearceerde gebied het datumbereikfilter dat u in het overzicht hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="eb224-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="eb224-223">U klikken en slepen om een specifiek begin- en eindpunt te selecteren, <u>waarin de gegevens worden gewijzigd die worden weergegeven in het gebied **Impact** en op de rest van de pagina zoals beschreven in de volgende secties</u>.</span><span class="sxs-lookup"><span data-stu-id="eb224-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="eb224-224">Klik op de titelbalk op het **schrijfpictogram campagne downloaden** ![ downloaden om de ](../../media/download-campaign-write-up-button.png) campagnedetails te downloaden naar een Word-document (standaard met de naam CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="eb224-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="eb224-225">Houd er rekening mee dat dit document details bevat over de gehele levensduur van de campagne (niet alleen de filterdatums die u hebt geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="eb224-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Campagne-informatie](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="eb224-227">Campagnestroom</span><span class="sxs-lookup"><span data-stu-id="eb224-227">Campaign flow</span></span>

<span data-ttu-id="eb224-228">In het midden van de weergave Campagnedetails worden belangrijke details over de campagne weergegeven in de sectie **Stroom** in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)._</span><span class="sxs-lookup"><span data-stu-id="eb224-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="eb224-229">Deze details helpen u om de elementen van de campagne en de mogelijke impact in uw organisatie te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="eb224-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="eb224-230">De informatie die wordt weergegeven in het **diagram Stroom** wordt beheerd door het gearceerde datumbereik in de tijdlijn zoals beschreven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="eb224-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Campagnegegevens die geen URL-klikken van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="eb224-232">Als u over een horizontale band in het diagram beweegt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaalde bron-IP, berichten van het bron-IP-adres met het opgegeven afzenderdomein, enz.).</span><span class="sxs-lookup"><span data-stu-id="eb224-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="eb224-233">Het diagram bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="eb224-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="eb224-234">**Ip's van afzenders**</span><span class="sxs-lookup"><span data-stu-id="eb224-234">**Sender IPs**</span></span>

- <span data-ttu-id="eb224-235">**Afzenderdomeinen**</span><span class="sxs-lookup"><span data-stu-id="eb224-235">**Sender domains**</span></span>

- <span data-ttu-id="eb224-236">**Filter vonnissen:** Deze waarden zijn gerelateerd aan de beschikbare phishing en spam filteren vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="eb224-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="eb224-237">De beschikbare waarden worden beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="eb224-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="eb224-238">**Value**</span><span class="sxs-lookup"><span data-stu-id="eb224-238">**Value**</span></span>|<span data-ttu-id="eb224-239">**Het oordeel van spamfilter**</span><span class="sxs-lookup"><span data-stu-id="eb224-239">**Spam filter verdict**</span></span>|<span data-ttu-id="eb224-240">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="eb224-240">**Description**</span></span>|
  |<span data-ttu-id="eb224-241">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="eb224-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="eb224-242">Het bericht is gemarkeerd als geen spam en/of overgeslagen filtering voordat het werd geëvalueerd door spamfilter (bijvoorbeeld door een mailflowregel, ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="eb224-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="eb224-243">Het bericht heeft spamfilters overgeslagen om andere redenen (bijvoorbeeld de afzender en ontvanger lijken zich in dezelfde organisatie te bevindt).</span><span class="sxs-lookup"><span data-stu-id="eb224-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="eb224-244">**Geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="eb224-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="eb224-245">Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfilter (bijvoorbeeld door een mailflowregel).</span><span class="sxs-lookup"><span data-stu-id="eb224-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="eb224-246">**Gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="eb224-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="eb224-247">Het bericht is gemarkeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="eb224-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="eb224-248">**Niet gedetecteerd**</span><span class="sxs-lookup"><span data-stu-id="eb224-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="eb224-249">Het bericht is gemarkeerd als geen spam door spamfiltering.</span><span class="sxs-lookup"><span data-stu-id="eb224-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="eb224-250">**Vrijgegeven**</span><span class="sxs-lookup"><span data-stu-id="eb224-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="eb224-251">Het bericht sloeg spamfiltering over omdat het uit quarantaine is vrijgekomen.</span><span class="sxs-lookup"><span data-stu-id="eb224-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="eb224-252">**Tenant toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="eb224-253">Het bericht heeft spamfilters overgeslagen vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="eb224-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="eb224-254">**Tenantblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="eb224-255">Het bericht is geblokkeerd door spamfilters vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de toegestane domeinlijst).</span><span class="sxs-lookup"><span data-stu-id="eb224-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="eb224-256">**Gebruiker toestaan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="eb224-257">Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="eb224-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="eb224-258">**Gebruikersblok**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="eb224-259">Het bericht is geblokkeerd door spamfilters omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.</span><span class="sxs-lookup"><span data-stu-id="eb224-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="eb224-260">**Zap**</span><span class="sxs-lookup"><span data-stu-id="eb224-260">**ZAP**</span></span>|<span data-ttu-id="eb224-261">N/a</span><span class="sxs-lookup"><span data-stu-id="eb224-261">n/a</span></span>|<span data-ttu-id="eb224-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) heeft actie ondernomen op het geleverde bericht volgens uw antispambeleidsinstellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).</span><span class="sxs-lookup"><span data-stu-id="eb224-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="eb224-263"><sup>\*</sup>Bekijk uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service zou zijn geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="eb224-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="eb224-264"><sup>\*\*</sup>Bekijk uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="eb224-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="eb224-265">**Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn bezorgd (naar de map Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de payload in het bericht hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="eb224-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="eb224-266">U de in quarantaine geplaatste berichten ook uit quarantaine verwijderen.</span><span class="sxs-lookup"><span data-stu-id="eb224-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="eb224-267">Zie [EOP in quarantaine geplaatst](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb224-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="eb224-268">**Verwijderde map**</span><span class="sxs-lookup"><span data-stu-id="eb224-268">**Deleted folder**</span></span>
  - <span data-ttu-id="eb224-269">**Gedaald**</span><span class="sxs-lookup"><span data-stu-id="eb224-269">**Dropped**</span></span>
  - <span data-ttu-id="eb224-270">**Extern**: De ontvanger bevindt zich in uw on-premises e-mailorganisatie in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="eb224-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="eb224-271">**Mislukt**</span><span class="sxs-lookup"><span data-stu-id="eb224-271">**Failed**</span></span>
  - <span data-ttu-id="eb224-272">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="eb224-272">**Forwarded**</span></span>
  - <span data-ttu-id="eb224-273">**Inbox**</span><span class="sxs-lookup"><span data-stu-id="eb224-273">**Inbox**</span></span>
  - <span data-ttu-id="eb224-274">**Ongewenste map**</span><span class="sxs-lookup"><span data-stu-id="eb224-274">**Junk folder**</span></span>
  - <span data-ttu-id="eb224-275">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="eb224-275">**Quarantine**</span></span>
  - <span data-ttu-id="eb224-276">**Unknown**</span><span class="sxs-lookup"><span data-stu-id="eb224-276">**Unknown**</span></span>

- <span data-ttu-id="eb224-277">**URL-klikken**: Deze worden beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="eb224-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="eb224-278">In alle lagen die meer dan 10 items bevatten, worden de top 10 items weergegeven, terwijl de rest is gebundeld in **anderen.**</span><span class="sxs-lookup"><span data-stu-id="eb224-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="eb224-279">URL-klikken</span><span class="sxs-lookup"><span data-stu-id="eb224-279">URL clicks</span></span>

<span data-ttu-id="eb224-280">Wanneer een phishingbericht wordt bezorgd bij een ontvanger (naar de postvak IN of de map Ongewenste e-mail), is er altijd een kans dat de gebruiker op de URL van de payload klikt.</span><span class="sxs-lookup"><span data-stu-id="eb224-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="eb224-281">Niet te klikken op de URL in een geleverd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.</span><span class="sxs-lookup"><span data-stu-id="eb224-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="eb224-282">Als een gebruiker op de URL van de payload in het phishingbericht heeft geklikt, worden de acties weergegeven in het gebied met **URL-klikken** van het diagram in de weergave campagnegegevens.</span><span class="sxs-lookup"><span data-stu-id="eb224-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="eb224-283">**Toegestaan**</span><span class="sxs-lookup"><span data-stu-id="eb224-283">**Allowed**</span></span>

- <span data-ttu-id="eb224-284">**BlockPage**: De ontvanger klikte op de payload-URL, maar de toegang tot de schadelijke website is geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eb224-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="eb224-285">**BlockPageOverride**: De ontvanger klikte op de payload-URL in het bericht, ATP Safe Links probeerde ze te stoppen, maar ze mochten het blok overschrijven.</span><span class="sxs-lookup"><span data-stu-id="eb224-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="eb224-286">U moet uw [beleid voor veilige links](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis Veilige links mogen negeren en doorgaan naar de kwaadaardige website.</span><span class="sxs-lookup"><span data-stu-id="eb224-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="eb224-287">**In afwachtingdetonationPage:** ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.</span><span class="sxs-lookup"><span data-stu-id="eb224-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="eb224-288">**PendingDetonationPageOverride**: De ontvanger mocht het payload detonatieproces overschrijven en de URL openen zonder te wachten op de resultaten.</span><span class="sxs-lookup"><span data-stu-id="eb224-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="eb224-289">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="eb224-289">Tabs</span></span>

<span data-ttu-id="eb224-290">Met de tabbladen in de campagnedetailsweergave u de campagne verder onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="eb224-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="eb224-291">De informatie die op de tabbladen wordt weergegeven, wordt beheerd door het gearceerde datumbereik in de tijdlijn zoals beschreven in de sectie [Campagnegegevens.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="eb224-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="eb224-292">**URL-klikken**: Als gebruikers niet op de URL van de payload in het phishingbericht hebben geklikt, is deze sectie leeg.</span><span class="sxs-lookup"><span data-stu-id="eb224-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="eb224-293">Als een gebruiker op de URL heeft kunnen klikken, worden de volgende waarden ingevuld:</span><span class="sxs-lookup"><span data-stu-id="eb224-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="eb224-294">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="eb224-295">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="eb224-296">**Kliktijd**</span><span class="sxs-lookup"><span data-stu-id="eb224-296">**Click time**</span></span>
  - <span data-ttu-id="eb224-297">**Klik op vonnis**</span><span class="sxs-lookup"><span data-stu-id="eb224-297">**Click verdict**</span></span>

- <span data-ttu-id="eb224-298">**Ip's van afzenders**</span><span class="sxs-lookup"><span data-stu-id="eb224-298">**Sender IPs**</span></span>

  - <span data-ttu-id="eb224-299">**IP-adres van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="eb224-300">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="eb224-300">**Total count**</span></span>
  - <span data-ttu-id="eb224-301">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="eb224-301">**Inboxed**</span></span>
  - <span data-ttu-id="eb224-302">**Niet inbox**</span><span class="sxs-lookup"><span data-stu-id="eb224-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="eb224-303">**SPF geslaagd**: De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="eb224-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="eb224-304">Een afzender die de SPF-validatie niet doorgeeft, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="eb224-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="eb224-305">**Afzenders**</span><span class="sxs-lookup"><span data-stu-id="eb224-305">**Senders**</span></span>

  - <span data-ttu-id="eb224-306">**Afzender**: Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, dat niet noodzakelijkerwijs het E-mailadres van: e-mailadres is dat gebruikers in hun e-mailclients zien.</span><span class="sxs-lookup"><span data-stu-id="eb224-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="eb224-307">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="eb224-307">**Total count**</span></span>
  - <span data-ttu-id="eb224-308">**Inboxed**</span><span class="sxs-lookup"><span data-stu-id="eb224-308">**Inboxed**</span></span>
  - <span data-ttu-id="eb224-309">**Niet inbox**</span><span class="sxs-lookup"><span data-stu-id="eb224-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="eb224-310">**DKIM geslaagd**: De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="eb224-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="eb224-311">Een afzender die de DKIM-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="eb224-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="eb224-312">**DMARC geslaagd**: De afzender is geverifieerd door [domeinverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="eb224-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="eb224-313">Een afzender die de DMARC-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.</span><span class="sxs-lookup"><span data-stu-id="eb224-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="eb224-314">**Bijlagen**</span><span class="sxs-lookup"><span data-stu-id="eb224-314">**Attachments**</span></span>

  - <span data-ttu-id="eb224-315">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="eb224-315">**Filename**</span></span>
  - <span data-ttu-id="eb224-316">**SHA256 SHA256**</span><span class="sxs-lookup"><span data-stu-id="eb224-316">**SHA256**</span></span>
  - <span data-ttu-id="eb224-317">**Malware familie**</span><span class="sxs-lookup"><span data-stu-id="eb224-317">**Malware family**</span></span>
  - <span data-ttu-id="eb224-318">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="eb224-318">**Total count**</span></span>

- <span data-ttu-id="eb224-319">**Url**</span><span class="sxs-lookup"><span data-stu-id="eb224-319">**URL**</span></span>

  - <span data-ttu-id="eb224-320">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="eb224-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="eb224-321">**Totaal aantal**</span><span class="sxs-lookup"><span data-stu-id="eb224-321">**Total Count**</span></span>

<span data-ttu-id="eb224-322"><sup>\*</sup>Als u op deze waarde klikt, opent u een nieuwe flyout met meer details over het opgegeven item (gebruiker, URL, enz.) boven in de weergave campagnedetails.</span><span class="sxs-lookup"><span data-stu-id="eb224-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="eb224-323">Als u wilt terugkeren naar de weergave Campagnedetails, klikt u op **Gereed** in de nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="eb224-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="eb224-324">Knoppen</span><span class="sxs-lookup"><span data-stu-id="eb224-324">Buttons</span></span>

<span data-ttu-id="eb224-325">Met de knoppen in de campagnedetailsweergave u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="eb224-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="eb224-326">**Campagne verkennen:** hiermee opent u een nieuw tabblad Bedreigingsverkenner met de waarde **campagne-id** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="eb224-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="eb224-327">**Inboxberichten verkennen:** opent een nieuw zoektabblad bedreigingsverkenner met behulp van de **campagne-id** en **de locatie Levering: Postvak IN** als zoekfilter.</span><span class="sxs-lookup"><span data-stu-id="eb224-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
