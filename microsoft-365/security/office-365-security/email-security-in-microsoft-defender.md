---
title: E-mailbeveiliging met Threat Explorer in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Malware phishingpogingen bekijken en onderzoeken.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cebe76536c5ed309ca16777e85c5cdf919d0fb5c
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082994"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="48739-103">E-mailbeveiliging met Threat Explorer in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="48739-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="48739-104">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="48739-104">In this article:</span></span>

- [<span data-ttu-id="48739-105">Malware weergeven die is gedetecteerd in e-mail</span><span class="sxs-lookup"><span data-stu-id="48739-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="48739-106">Phishing-URL weergeven en op vonnisgegevens klikken</span><span class="sxs-lookup"><span data-stu-id="48739-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="48739-107">Geautomatiseerde onderzoeken en antwoorden starten</span><span class="sxs-lookup"><span data-stu-id="48739-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="48739-108">Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken).</span><span class="sxs-lookup"><span data-stu-id="48739-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="48739-109">De andere twee artikelen in deze reeks zijn [Bedreigingsjacht in Threat Explorer](threat-hunting-in-threat-explorer.md) en Threat Explorer en de basisbeginselen van [realtimedetecties.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="48739-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>

<span data-ttu-id="48739-110">In dit artikel wordt uitgelegd hoe u malware- en phishingpogingen kunt bekijken en onderzoeken die worden gedetecteerd in e-mail door Microsoft 365 beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="48739-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span>

<span data-ttu-id="48739-111">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48739-111">**Applies to:**</span></span>

- [<span data-ttu-id="48739-112">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="48739-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="48739-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48739-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="48739-114">Malware weergeven die is gedetecteerd in e-mail</span><span class="sxs-lookup"><span data-stu-id="48739-114">View malware detected in email</span></span>

<span data-ttu-id="48739-115">Als u malware wilt zien die is gedetecteerd in [**\>**](threat-explorer-views.md#email--malware) e-mail die is gesorteerd op Microsoft 365 technologie, gebruikt u de weergave E-mail malware van Explorer (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="48739-115">To see malware detected in email sorted by Microsoft 365 technology, use the [**Email \> Malware**](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="48739-116">Malware is de standaardweergave, dus deze kan worden geselecteerd zodra u Verkenner opent.</span><span class="sxs-lookup"><span data-stu-id="48739-116">Malware is the default view, so it might be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="48739-117">Kies in Microsoft 365 Defender portal ( ) de optie <https://security.microsoft.com> **E-mail & Explorer** voor samenwerking \>  (of **Realtime detecties;** In dit voorbeeld wordt Explorer gebruikt).</span><span class="sxs-lookup"><span data-stu-id="48739-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

   <span data-ttu-id="48739-118">Vanaf hier begint u bij de weergave, kiest u een bepaald tijdsbestek om het te onderzoeken (indien nodig) en richt u de filters op de [verkenner.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="48739-118">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="48739-119">Controleer in **de** vervolgkeuzelijst Weergave of **E-mail** \> **malware** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="48739-119">In the **View** drop down list, verify that **Email** \> **Malware** is selected.</span></span>

3. <span data-ttu-id="48739-120">Klik **op Afzender** en kies vervolgens **Basisdetectietechnologie** in de \>  vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="48739-120">Click **Sender**, and then choose **Basic** \> **Detection technology** in the drop down list.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="malwaredetectietechnologie":::

   <span data-ttu-id="48739-122">Uw detectietechnologieën zijn nu beschikbaar als filters voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="48739-122">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="48739-123">Kies een optie en klik vervolgens op **Vernieuwen om** dat filter toe te passen (vernieuw het browservenster niet).</span><span class="sxs-lookup"><span data-stu-id="48739-123">Choose an option, and then click **Refresh** to apply that filter (don't refresh your browser window).</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="geselecteerde detectietechnologie":::

   <span data-ttu-id="48739-125">Het rapport wordt vernieuwd om de resultaten weer te geven die malware heeft gedetecteerd in e-mail, met de technologieoptie die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="48739-125">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="48739-126">Hier kunt u verdere analyse uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="48739-126">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="48739-127">Phishing-URL weergeven en op vonnisgegevens klikken</span><span class="sxs-lookup"><span data-stu-id="48739-127">View phishing URL and click verdict data</span></span>

<span data-ttu-id="48739-128">U kunt phishingpogingen via URL's in e-mail bekijken, inclusief een lijst met URL's die zijn toegestaan, geblokkeerd en overschrijven.</span><span class="sxs-lookup"><span data-stu-id="48739-128">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="48739-129">Als u URL's wilt identificeren waar op is geklikt, [Safe koppelingen](safe-links.md) moeten worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="48739-129">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="48739-130">Zorg ervoor dat u het beleid Safe [koppelingen](set-up-safe-links-policies.md) in te stellen voor time-of-click beveiliging en logboekregistratie van klik-uitspraken door Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="48739-130">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

1. <span data-ttu-id="48739-131">Kies in Microsoft 365 Defender portal ( ) de optie <https://security.microsoft.com> **E-mail & Explorer** voor samenwerking \>  (of **Realtime detecties;** In dit voorbeeld wordt Explorer gebruikt).</span><span class="sxs-lookup"><span data-stu-id="48739-131">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**; This example uses Explorer).</span></span>

2. <span data-ttu-id="48739-132">Kies in **de** vervolgkeuzelijst Weergave de optie **E-mail** \> **phish**.</span><span class="sxs-lookup"><span data-stu-id="48739-132">In the **View** drop down list, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48739-133">![Menu Weergeven voor Explorer in phishing-context](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="48739-133">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="48739-134">Klik **op Afzender** en kies **URL's Klik** op \> **vonnis** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="48739-134">Click **Sender**, and then choose **URLs** \> **Click verdict** in the drop down list.</span></span>

4. <span data-ttu-id="48739-135">Selecteer in de opties die worden weergegeven  een of meer opties, zoals Geblokkeerd en Geblokkeerd, en klik vervolgens op Vernieuwen **(vernieuw** het browservenster niet).</span><span class="sxs-lookup"><span data-stu-id="48739-135">In options that appear, select one or more options, such as **Blocked** and **Block overridden**, and then click **Refresh** (don't refresh your browser window).</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL's en klik op vonnissen":::

   <span data-ttu-id="48739-137">Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad **URL's** onder het rapport:</span><span class="sxs-lookup"><span data-stu-id="48739-137">The report refreshes to show two different URL tables on the **URLs** tab under the report:</span></span>

   - <span data-ttu-id="48739-138">**Top-URL's** zijn de URL's in de berichten die u hebt gefilterd en de actie voor e-mailbezorging telt voor elke URL.</span><span class="sxs-lookup"><span data-stu-id="48739-138">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="48739-139">In de phish-e-mailweergave bevat deze lijst meestal legitieme URL's.</span><span class="sxs-lookup"><span data-stu-id="48739-139">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="48739-140">Aanvallers bevatten een combinatie van goede en slechte URL's in hun berichten om te proberen ze bezorgd te krijgen, maar ze maken de schadelijke koppelingen interessanter.</span><span class="sxs-lookup"><span data-stu-id="48739-140">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="48739-141">De tabel met URL's wordt gesorteerd op totaal aantal e-mail, maar deze kolom is verborgen om de weergave te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="48739-141">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="48739-142">**De bovenste klikken** zijn de Safe url's met koppelingen die zijn geklikt, gesorteerd op het totale aantal klikken.</span><span class="sxs-lookup"><span data-stu-id="48739-142">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="48739-143">Deze kolom wordt ook niet weergegeven, om de weergave te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="48739-143">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="48739-144">Het totaal aantal per kolom geeft aan Safe aantal klikken op vonnissen voor elke geklikte URL.</span><span class="sxs-lookup"><span data-stu-id="48739-144">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="48739-145">In de phish-e-mailweergave zijn dit meestal verdachte of schadelijke URL's.</span><span class="sxs-lookup"><span data-stu-id="48739-145">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="48739-146">Maar de weergave kan URL's bevatten die geen bedreigingen zijn, maar in phish-berichten staan.</span><span class="sxs-lookup"><span data-stu-id="48739-146">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="48739-147">URL-klikken op niet-uitpakte koppelingen worden hier niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="48739-147">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="48739-148">De twee URL-tabellen bevatten de beste URL's in phishing-e-mailberichten op bezorgingsactie en locatie.</span><span class="sxs-lookup"><span data-stu-id="48739-148">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="48739-149">In de tabellen worden URL-klikken weergegeven die ondanks een waarschuwing zijn geblokkeerd of bezocht, zodat u kunt zien welke mogelijke slechte koppelingen aan gebruikers zijn gepresenteerd en waar de gebruikers op hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="48739-149">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="48739-150">Hier kunt u verdere analyse uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="48739-150">From here, you can conduct further analysis.</span></span> <span data-ttu-id="48739-151">Onder de grafiek ziet u bijvoorbeeld de bovenste URL's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="48739-151">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48739-152">![Explorer-URL's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="48739-152">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="48739-153">Selecteer een URL om meer gedetailleerde informatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="48739-153">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48739-154">In het dialoogvenster URL-flyout wordt het filteren op e-mailberichten verwijderd om de volledige weergave van de blootstelling van de URL in uw omgeving weer te geven.</span><span class="sxs-lookup"><span data-stu-id="48739-154">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="48739-155">Hiermee kunt u filteren op e-mailberichten waar u zich zorgen over maakt in Verkenner, specifieke URL's zoeken die potentiële bedreigingen zijn en vervolgens uw inzicht in de blootstelling aan URL's in uw omgeving uitbreiden (via het dialoogvenster URL-details) zonder URL-filters toe te voegen aan de Verkenner-weergave zelf.</span><span class="sxs-lookup"><span data-stu-id="48739-155">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="48739-156">Interpretatie van click-vonnissen</span><span class="sxs-lookup"><span data-stu-id="48739-156">Interpretation of click verdicts</span></span>

<span data-ttu-id="48739-157">In de fly-outs E-mail of URL, TopKlikken en in onze filterervaringen ziet u verschillende waarden voor klikuitspraken:</span><span class="sxs-lookup"><span data-stu-id="48739-157">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="48739-158">**Geen:** Kan de uitspraak voor de URL niet vastleggen.</span><span class="sxs-lookup"><span data-stu-id="48739-158">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="48739-159">De gebruiker heeft mogelijk door de URL geklikt.</span><span class="sxs-lookup"><span data-stu-id="48739-159">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="48739-160">**Toegestaan:** De gebruiker mocht naar de URL navigeren.</span><span class="sxs-lookup"><span data-stu-id="48739-160">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="48739-161">**Geblokkeerd:** De gebruiker is geblokkeerd om naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="48739-161">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="48739-162">**Vonnis in behandeling:** De gebruiker heeft de pagina met detonatie in behandeling.</span><span class="sxs-lookup"><span data-stu-id="48739-162">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="48739-163">**Geblokkeerde overschrijven:** De gebruiker is geblokkeerd om rechtstreeks naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="48739-163">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="48739-164">Maar de gebruiker overdroeed het blok om naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="48739-164">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="48739-165">**Vonnis in behandeling is omzeild:** De gebruiker kreeg de detonatiepagina te zien.</span><span class="sxs-lookup"><span data-stu-id="48739-165">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="48739-166">Maar de gebruiker overdroeed het bericht om toegang te krijgen tot de URL.</span><span class="sxs-lookup"><span data-stu-id="48739-166">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="48739-167">**Fout:** De gebruiker heeft de foutpagina te zien of er is een fout opgetreden bij het vastleggen van de uitspraak.</span><span class="sxs-lookup"><span data-stu-id="48739-167">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="48739-168">**Fout:** Er is een onbekende uitzondering opgetreden tijdens het vastleggen van de uitspraak.</span><span class="sxs-lookup"><span data-stu-id="48739-168">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="48739-169">De gebruiker heeft mogelijk door de URL geklikt.</span><span class="sxs-lookup"><span data-stu-id="48739-169">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="48739-170">Geautomatiseerde onderzoeken en antwoorden starten</span><span class="sxs-lookup"><span data-stu-id="48739-170">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="48739-171">Geautomatiseerde onderzoeks- en antwoordmogelijkheden zijn beschikbaar in *Microsoft Defender voor Office 365 Plan 2* en *Office 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="48739-171">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="48739-172">[Geautomatiseerde onderzoeken en antwoorden kunnen](automated-investigation-response-office.md) uw teamtijd en inspanning voor beveiligingsactiviteiten besparen bij het onderzoeken en verminderen van cyberaanvallen.</span><span class="sxs-lookup"><span data-stu-id="48739-172">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="48739-173">Naast het configureren van waarschuwingen die een beveiligingss playbook kunnen activeren, kunt u een geautomatiseerd onderzoek en antwoordproces starten vanuit een weergave in Explorer.</span><span class="sxs-lookup"><span data-stu-id="48739-173">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="48739-174">Zie Voorbeeld: Een beveiligingsbeheerder activeert een onderzoek [vanuit Verkenner voor meer informatie.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="48739-174">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="48739-175">Andere artikelen</span><span class="sxs-lookup"><span data-stu-id="48739-175">Other articles</span></span>

[<span data-ttu-id="48739-176">E-mailberichten onderzoeken met de pagina E-mailentiteit</span><span class="sxs-lookup"><span data-stu-id="48739-176">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
