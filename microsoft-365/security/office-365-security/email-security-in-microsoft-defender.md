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
ms.openlocfilehash: a2a6d3d10cfa21c0ad2da948bff130cb9336ebd8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297621"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2687a-103">E-mailbeveiliging met Threat Explorer in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2687a-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2687a-104">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="2687a-104">In this article:</span></span>

- [<span data-ttu-id="2687a-105">Malware weergeven die is gedetecteerd in e-mail</span><span class="sxs-lookup"><span data-stu-id="2687a-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="2687a-106">Phishing-URL weergeven en op vonnisgegevens klikken</span><span class="sxs-lookup"><span data-stu-id="2687a-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="2687a-107">Geautomatiseerde onderzoeken en antwoorden starten</span><span class="sxs-lookup"><span data-stu-id="2687a-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="2687a-108">Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken).</span><span class="sxs-lookup"><span data-stu-id="2687a-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="2687a-109">De andere twee artikelen in deze reeks zijn [Bedreigingsjacht in Threat Explorer](threat-hunting-in-threat-explorer.md) en Threat Explorer en de basisbeginselen van [realtimedetecties.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="2687a-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="2687a-110">In dit artikel wordt uitgelegd hoe u malware- en phishingpogingen kunt bekijken en onderzoeken die worden gedetecteerd in e-mail door Microsoft 365 beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="2687a-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="2687a-111">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2687a-111">**Applies to**</span></span>

- [<span data-ttu-id="2687a-112">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2687a-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2687a-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2687a-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="2687a-114">Malware weergeven die is gedetecteerd in e-mail</span><span class="sxs-lookup"><span data-stu-id="2687a-114">View malware detected in email</span></span>

<span data-ttu-id="2687a-115">Als u malware wilt zien die is gedetecteerd in e-mail die is gesorteerd op Microsoft 365 technologie, gebruikt u de weergave E-mail [> Malware](threat-explorer-views.md#email--malware) van Explorer (of Realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="2687a-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="2687a-116">Malware is de standaardweergave, dus deze kan worden geselecteerd zodra u Verkenner opent.</span><span class="sxs-lookup"><span data-stu-id="2687a-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="2687a-117">Kies in & Beveiligingscentrum <https://protection.office.com> () **de** optie Threat Management \> **Explorer** (of **Realtime detecties).**</span><span class="sxs-lookup"><span data-stu-id="2687a-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="2687a-118">(In dit voorbeeld wordt Verkenner gebruikt.) Als u zich in het geconvergeerde beveiligingscentrum Microsoft 365 ( https://security.microsoft.com/) schuif naar **E-mail & Explorer samenwerking**  >  .</span><span class="sxs-lookup"><span data-stu-id="2687a-118">(This example uses Explorer.) If you're in the converged Microsoft 365 security center (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="2687a-119">Vanaf hier begint u bij de weergave, kiest u een bepaald tijdsbestek om het te onderzoeken (indien nodig) en richt u de filters op de [verkenner.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="2687a-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="2687a-120">Kies in **het** menu Beeld de optie **E-mail** \> **malware.**</span><span class="sxs-lookup"><span data-stu-id="2687a-120">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-121">![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-121">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="2687a-122">Klik **op Afzender** en kies vervolgens **Basisdetectietechnologie.** \> </span><span class="sxs-lookup"><span data-stu-id="2687a-122">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="2687a-123">Uw detectietechnologieën zijn nu beschikbaar als filters voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="2687a-123">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-124">![Technologieën voor malwaredetectie](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-124">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="2687a-125">Kies een optie.</span><span class="sxs-lookup"><span data-stu-id="2687a-125">Choose an option.</span></span> <span data-ttu-id="2687a-126">Selecteer vervolgens de **knop Vernieuwen** om dat filter toe te passen.</span><span class="sxs-lookup"><span data-stu-id="2687a-126">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-127">![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-127">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="2687a-128">Het rapport wordt vernieuwd om de resultaten weer te geven die malware heeft gedetecteerd in e-mail, met de technologieoptie die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2687a-128">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="2687a-129">Hier kunt u verdere analyse uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-129">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="2687a-130">Phishing-URL weergeven en op vonnisgegevens klikken</span><span class="sxs-lookup"><span data-stu-id="2687a-130">View phishing URL and click verdict data</span></span>

<span data-ttu-id="2687a-131">U kunt phishingpogingen via URL's in e-mail bekijken, inclusief een lijst met URL's die zijn toegestaan, geblokkeerd en overschrijven.</span><span class="sxs-lookup"><span data-stu-id="2687a-131">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="2687a-132">Als u URL's wilt identificeren waar op is geklikt, [Safe koppelingen](safe-links.md) moeten worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="2687a-132">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="2687a-133">Zorg ervoor dat u het beleid Safe [koppelingen](set-up-safe-links-policies.md) in te stellen voor time-of-click beveiliging en logboekregistratie van klik-uitspraken door Safe koppelingen.</span><span class="sxs-lookup"><span data-stu-id="2687a-133">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="2687a-134">Als u phish-URL's in berichten wilt bekijken en op URL's in phish-berichten wilt klikken, gebruikt u de weergave [ **E-mail**  >  **phish**](threat-explorer-views.md#email--phish) van Explorer of realtime detecties.</span><span class="sxs-lookup"><span data-stu-id="2687a-134">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="2687a-135">Kies in & Beveiligingscentrum <https://protection.office.com> () **de** optie Threat Management \> **Explorer** (of **Realtime detecties).**</span><span class="sxs-lookup"><span data-stu-id="2687a-135">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="2687a-136">(In dit voorbeeld wordt Verkenner gebruikt.)</span><span class="sxs-lookup"><span data-stu-id="2687a-136">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="2687a-137">Kies in **het** menu Beeld de optie **E-mail** \> **phish**.</span><span class="sxs-lookup"><span data-stu-id="2687a-137">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-138">![Menu Weergeven voor Explorer in phishing-context](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-138">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="2687a-139">Klik **op Afzender** en kies **URL's Klik** op \> **vonnis.**</span><span class="sxs-lookup"><span data-stu-id="2687a-139">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="2687a-140">Selecteer een of meer opties, zoals **Geblokkeerd** en Geblokkeerd,  en selecteer vervolgens de knop Vernieuwen op dezelfde regel als de opties om dat filter toe te passen.</span><span class="sxs-lookup"><span data-stu-id="2687a-140">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="2687a-141">(Vernieuw het browservenster niet.)</span><span class="sxs-lookup"><span data-stu-id="2687a-141">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-142">![URL's en klik op vonnissen](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-142">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="2687a-143">Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:</span><span class="sxs-lookup"><span data-stu-id="2687a-143">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="2687a-144">**Top-URL's** zijn de URL's in de berichten die u hebt gefilterd en de actie voor e-mailbezorging telt voor elke URL.</span><span class="sxs-lookup"><span data-stu-id="2687a-144">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="2687a-145">In de phish-e-mailweergave bevat deze lijst meestal legitieme URL's.</span><span class="sxs-lookup"><span data-stu-id="2687a-145">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="2687a-146">Aanvallers bevatten een combinatie van goede en slechte URL's in hun berichten om te proberen ze bezorgd te krijgen, maar ze maken de schadelijke koppelingen interessanter.</span><span class="sxs-lookup"><span data-stu-id="2687a-146">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="2687a-147">De tabel met URL's wordt gesorteerd op totaal aantal e-mail, maar deze kolom is verborgen om de weergave te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="2687a-147">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="2687a-148">**De bovenste klikken** zijn de Safe url's met koppelingen die zijn geklikt, gesorteerd op het totale aantal klikken.</span><span class="sxs-lookup"><span data-stu-id="2687a-148">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="2687a-149">Deze kolom wordt ook niet weergegeven, om de weergave te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="2687a-149">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="2687a-150">Het totaal aantal per kolom geeft aan Safe aantal klikken op vonnissen voor elke geklikte URL.</span><span class="sxs-lookup"><span data-stu-id="2687a-150">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="2687a-151">In de phish-e-mailweergave zijn dit meestal verdachte of schadelijke URL's.</span><span class="sxs-lookup"><span data-stu-id="2687a-151">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="2687a-152">Maar de weergave kan URL's bevatten die geen bedreigingen zijn, maar in phish-berichten staan.</span><span class="sxs-lookup"><span data-stu-id="2687a-152">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="2687a-153">URL-klikken op niet-uitpakte koppelingen worden hier niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2687a-153">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="2687a-154">De twee URL-tabellen bevatten de beste URL's in phishing-e-mailberichten op bezorgingsactie en locatie.</span><span class="sxs-lookup"><span data-stu-id="2687a-154">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="2687a-155">In de tabellen worden URL-klikken weergegeven die ondanks een waarschuwing zijn geblokkeerd of bezocht, zodat u kunt zien welke mogelijke slechte koppelingen aan gebruikers zijn gepresenteerd en waar de gebruikers op hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="2687a-155">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="2687a-156">Hier kunt u verdere analyse uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-156">From here, you can conduct further analysis.</span></span> <span data-ttu-id="2687a-157">Onder de grafiek ziet u bijvoorbeeld de bovenste URL's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2687a-157">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2687a-158">![Explorer-URL's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="2687a-158">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="2687a-159">Selecteer een URL om meer gedetailleerde informatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2687a-159">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2687a-160">In het dialoogvenster URL-flyout wordt het filteren op e-mailberichten verwijderd om de volledige weergave van de blootstelling van de URL in uw omgeving weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2687a-160">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="2687a-161">Hiermee kunt u filteren op e-mailberichten waar u zich zorgen over maakt in Verkenner, specifieke URL's zoeken die potentiële bedreigingen zijn en vervolgens uw inzicht in de blootstelling aan URL's in uw omgeving uitbreiden (via het dialoogvenster URL-details) zonder URL-filters toe te voegen aan de Verkenner-weergave zelf.</span><span class="sxs-lookup"><span data-stu-id="2687a-161">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="2687a-162">Interpretatie van click-vonnissen</span><span class="sxs-lookup"><span data-stu-id="2687a-162">Interpretation of click verdicts</span></span>

<span data-ttu-id="2687a-163">In de fly-outs E-mail of URL, TopKlikken en in onze filterervaringen ziet u verschillende waarden voor klikuitspraken:</span><span class="sxs-lookup"><span data-stu-id="2687a-163">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="2687a-164">**Geen:** Kan de uitspraak voor de URL niet vastleggen.</span><span class="sxs-lookup"><span data-stu-id="2687a-164">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="2687a-165">De gebruiker heeft mogelijk door de URL geklikt.</span><span class="sxs-lookup"><span data-stu-id="2687a-165">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="2687a-166">**Toegestaan:** De gebruiker mocht naar de URL navigeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-166">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="2687a-167">**Geblokkeerd:** De gebruiker is geblokkeerd om naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-167">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="2687a-168">**Vonnis in behandeling:** De gebruiker heeft de pagina met detonatie in behandeling.</span><span class="sxs-lookup"><span data-stu-id="2687a-168">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="2687a-169">**Geblokkeerde overschrijven:** De gebruiker is geblokkeerd om rechtstreeks naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-169">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="2687a-170">Maar de gebruiker overdroeed het blok om naar de URL te navigeren.</span><span class="sxs-lookup"><span data-stu-id="2687a-170">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="2687a-171">**Vonnis in behandeling is omzeild:** De gebruiker kreeg de detonatiepagina te zien.</span><span class="sxs-lookup"><span data-stu-id="2687a-171">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="2687a-172">Maar de gebruiker overdroeed het bericht om toegang te krijgen tot de URL.</span><span class="sxs-lookup"><span data-stu-id="2687a-172">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="2687a-173">**Fout:** De gebruiker heeft de foutpagina te zien of er is een fout opgetreden bij het vastleggen van de uitspraak.</span><span class="sxs-lookup"><span data-stu-id="2687a-173">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="2687a-174">**Fout:** Er is een onbekende uitzondering opgetreden tijdens het vastleggen van de uitspraak.</span><span class="sxs-lookup"><span data-stu-id="2687a-174">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="2687a-175">De gebruiker heeft mogelijk door de URL geklikt.</span><span class="sxs-lookup"><span data-stu-id="2687a-175">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="2687a-176">Geautomatiseerde onderzoeken en antwoorden starten</span><span class="sxs-lookup"><span data-stu-id="2687a-176">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="2687a-177">Geautomatiseerde onderzoeks- en antwoordmogelijkheden zijn beschikbaar in *Microsoft Defender voor Office 365 Plan 2* en Office 365 *E5.*</span><span class="sxs-lookup"><span data-stu-id="2687a-177">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="2687a-178">[Geautomatiseerde onderzoeken en antwoorden kunnen](automated-investigation-response-office.md) uw teamtijd en inspanning voor beveiligingsactiviteiten besparen bij het onderzoeken en verminderen van cyberaanvallen.</span><span class="sxs-lookup"><span data-stu-id="2687a-178">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="2687a-179">Naast het configureren van waarschuwingen die een beveiligingss playbook kunnen activeren, kunt u een geautomatiseerd onderzoek en antwoordproces starten vanuit een weergave in Explorer.</span><span class="sxs-lookup"><span data-stu-id="2687a-179">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="2687a-180">Zie Voorbeeld: Een beveiligingsbeheerder activeert een onderzoek [vanuit Verkenner voor meer informatie.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)</span><span class="sxs-lookup"><span data-stu-id="2687a-180">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="2687a-181">Andere artikelen</span><span class="sxs-lookup"><span data-stu-id="2687a-181">Other articles</span></span>

[<span data-ttu-id="2687a-182">E-mailberichten onderzoeken met de pagina E-mailentiteit</span><span class="sxs-lookup"><span data-stu-id="2687a-182">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
