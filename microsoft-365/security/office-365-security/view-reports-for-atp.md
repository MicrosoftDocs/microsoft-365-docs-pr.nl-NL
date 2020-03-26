---
title: Rapporten weergeven voor Office 365 Advanced Threat Protection, malwarerapporten, phish-rapporten, gecompromitteerde accounts, URL-beveiligingsstatus, bedreigingsrapportage, meldingen van bedreigingen
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 02/07/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Rapporten zoeken en gebruiken voor Geavanceerde bedreigingsbeveiliging &amp; van Office 365 in het Security Compliance Center.
ms.openlocfilehash: d65df770b91faf4530701b982e8ba6fa15ddf333
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955507"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="24d58-103">Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="24d58-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="24d58-104">Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) heeft en u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)beschikt, u verschillende ATP-rapporten gebruiken in het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="24d58-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="24d58-105">(Ga naar **Dashboard Rapporten** \> **.)**</span><span class="sxs-lookup"><span data-stu-id="24d58-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Het &amp; dashboard van het Security Compliance Center kan u helpen te zien waar Advanced Threat Protection werkt](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="24d58-107">ATP-rapporten bevatten het volgende:</span><span class="sxs-lookup"><span data-stu-id="24d58-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="24d58-108">Rapport statusstatus bedreigingsbescherming</span><span class="sxs-lookup"><span data-stu-id="24d58-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="24d58-109">Rapport ATP-bestandstypen</span><span class="sxs-lookup"><span data-stu-id="24d58-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="24d58-110">RAPPORT ATP-berichtdispositie</span><span class="sxs-lookup"><span data-stu-id="24d58-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="24d58-111">[realtime detecties of Explorer](threat-explorer.md) (afhankelijk van of u Office 365 ATP Plan 1 of 2 hebt)</span><span class="sxs-lookup"><span data-stu-id="24d58-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="24d58-112">... [en meer](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="24d58-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="24d58-113">Lees dit artikel om een overzicht te krijgen van ATP-rapporten en hoe deze te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24d58-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="24d58-114">Rapport statusstatus bedreigingsbescherming</span><span class="sxs-lookup"><span data-stu-id="24d58-114">Threat Protection Status report</span></span>

<span data-ttu-id="24d58-115">Het rapport **Status van bedreigingsbescherming** is één weergave die informatie samenbrengt over schadelijke inhoud en schadelijke e-mail die wordt gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office [365 ATP.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="24d58-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="24d58-116">Dit rapport is handig voor het bekijken van detecties in de loop van de tijd (tot 90 dagen) en stelt beveiligingsbeheerders in staat om trends te identificeren of te bepalen of beleid aanpassingen nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="24d58-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="24d58-117">Het rapport biedt een geaggregeerdaantal van unieke e-mailberichten met schadelijke inhoud, zoals bestanden of website-adressen (URL's) die werden geblokkeerd door de anti-malware-engine, [zero-hour automatische zuivering (ZAP) en ATP-functies](zero-hour-auto-purge.md)zoals [ATP Safe Links,](atp-safe-links.md) [ATP Safe Attachments](atp-safe-attachments.md)en [ATP anti-phishing mogelijkheden](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="24d58-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

<span data-ttu-id="24d58-118">Filters en uitsplitsingen van de informatie zorgen voor meer gedetailleerde categorisaties van de informatie in dit rapport.</span><span class="sxs-lookup"><span data-stu-id="24d58-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="24d58-119">Specifiek, er is een 'break down by' menu opgenomen voor *e-mail > Phish* en *E-mail > Malware weergaven*.</span><span class="sxs-lookup"><span data-stu-id="24d58-119">Specifically, there is a 'break down by' menu included for *Email > Phish* and *Email > Malware views*.</span></span> <span data-ttu-id="24d58-120">Het zal de gegevens opsplitsen in:</span><span class="sxs-lookup"><span data-stu-id="24d58-120">It will break down the data into:</span></span>

| |  |
|---------|---------|
|<span data-ttu-id="24d58-121">Op detectietype</span><span class="sxs-lookup"><span data-stu-id="24d58-121">By detection type</span></span>    | <span data-ttu-id="24d58-122">Welk beleid heeft geholpen deze bedreigingen op te vangen?</span><span class="sxs-lookup"><span data-stu-id="24d58-122">What policy helped catch these threats?</span></span>         |
|<span data-ttu-id="24d58-123">Door detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="24d58-123">By detection technology</span></span>     | <span data-ttu-id="24d58-124">Welke onderliggende Microsoft-technologie ving de dreiging?</span><span class="sxs-lookup"><span data-stu-id="24d58-124">What underlying Microsoft technology caught the threat?</span></span>        |
|<span data-ttu-id="24d58-125">Op leveringsstatus</span><span class="sxs-lookup"><span data-stu-id="24d58-125">By delivery status</span></span>     | <span data-ttu-id="24d58-126">Wat is er gebeurd met de e-mailberichten gedetecteerd als bedreigingen?</span><span class="sxs-lookup"><span data-stu-id="24d58-126">What happened to the email messages detected as threats?</span></span>         |
| | |

> [!TIP]
> <span data-ttu-id="24d58-127">Zowel de e-mail > Phish | Malware weergaven hebben gedetailleerde uitsplitsingen voor de detectie technologieën getoond, met categorieën zoals *ATP-gegenereerde bestandsreputatie*, *File detonatie*, *URL-detonatie*, *Anti-spoof: DMARC mislukking*, bijvoorbeeld, nuttig bij het lokaliseren van precies welke functie leidde uw organisatie om bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="24d58-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Dropdown van de Status van bedreigingsstatus toont 'break down by'.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="24d58-129">Deze weergaven geven u de mogelijkheid om te exporteren, via een knop klik (in E-mail > Phish, E-mail > Malware, en Content > Malware weergaven).</span><span class="sxs-lookup"><span data-stu-id="24d58-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="24d58-130">De geaggregeerde gegevens die naar uw computer worden geëxporteerd, kunnen worden geopend in Excel.</span><span class="sxs-lookup"><span data-stu-id="24d58-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![In deze afbeelding wordt Exporteren als een optie weergegeven in het menu voor de weergave Malware, precies tussen Planning maken en Rapport aanvragen.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="24d58-132">In de overzichts- en e-mailsweergave worden binnen enkele uren na de verwerking informatie weergegeven in plaats van binnen 24 uur (vraag opnieuw.</span><span class="sxs-lookup"><span data-stu-id="24d58-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="24d58-133">verhoogde snelheden hier is een duidelijk signaal)!</span><span class="sxs-lookup"><span data-stu-id="24d58-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="24d58-134">Een rapport over de status van bedreigingsbescherming is beschikbaar voor klanten die [Office 365 ATP](office-365-atp.md) of [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) hebben; De informatie die wordt weergegeven in het rapport Status bedreigingsstatus voor ATP-klanten zal echter waarschijnlijk andere gegevens bevatten dan wat EOP-klanten kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="24d58-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="24d58-135">Het rapport Statusstatus bedreigingsbeveiliging voor ATP-klanten bevat bijvoorbeeld informatie over [schadelijke bestanden die zijn gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="24d58-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="24d58-136">Dergelijke informatie is specifiek voor ATP, dus klanten die EOP hebben maar geen ATP, zien deze gegevens niet in hun rapport over de status van bedreigingsbescherming.</span><span class="sxs-lookup"><span data-stu-id="24d58-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="24d58-137">Als u het rapport Status bedreigingsbeveiliging wilt weergeven, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar de **status bedreigingsbeveiliging** **van het** \> **dashboard** \> rapporten .</span><span class="sxs-lookup"><span data-stu-id="24d58-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP Threat Protection Status rapport](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="24d58-139">Als u een dag lang een gedetailleerde status wilt krijgen, zweeft u over de grafiek.</span><span class="sxs-lookup"><span data-stu-id="24d58-139">To get detailed status for a day, hover over the graph.</span></span>
  
![ATP Threat Protection Status gegevens voor een dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="24d58-141">Standaard worden in het rapport Status bedreigingsbeveiliging gegevens van de afgelopen zeven dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="24d58-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="24d58-142">U echter **filters** kiezen en het datumbereik wijzigen om gegevens maximaal 90 dagen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="24d58-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="24d58-143">(Als u een proefabonnement gebruikt, bent u mogelijk beperkt tot 30 dagen aan gegevens.)</span><span class="sxs-lookup"><span data-stu-id="24d58-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Filters voor atp-statusstatusvan de bescherming van bedreigingen](../../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="24d58-145">U ook het menu Gegevens per menu **weergeven** gebruiken om te wijzigen welke informatie in het rapport wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="24d58-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Opties weergeven voor het rapport STATUSvan ATP-dreigingsbescherming](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="24d58-147">Rapport URL-beveiligingsstatus</span><span class="sxs-lookup"><span data-stu-id="24d58-147">URL Protection Status report</span></span>

<span data-ttu-id="24d58-148">Dit rapport is gebaseerd op gegevens verzameld, en bedreigingen gedetecteerd, per klik (terwijl de meeste andere e-mail bedreiging gerelateerde rapporten zijn per bericht gegevens).</span><span class="sxs-lookup"><span data-stu-id="24d58-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="24d58-149">Dit rapport is ontworpen om bedreigingen weer te geven die afkomstig zijn van hyperlinks in e-mailberichten en documenten, per klik.</span><span class="sxs-lookup"><span data-stu-id="24d58-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="24d58-150">Er zijn twee weergaven:</span><span class="sxs-lookup"><span data-stu-id="24d58-150">There are two views:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="24d58-151">Actie voor URL-klikbeveiliging</span><span class="sxs-lookup"><span data-stu-id="24d58-151">URL click protection action</span></span>   | <span data-ttu-id="24d58-152">Bekijk het aantal geblokkeerde, geblokkeerde maar overschreven URL's met een doorklik door een gebruiker, wordt overschreven met een doorklik door een gebruiker en toegestaan.</span><span class="sxs-lookup"><span data-stu-id="24d58-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>        |
|<span data-ttu-id="24d58-153">URL klik per toepassing</span><span class="sxs-lookup"><span data-stu-id="24d58-153">URL click by application</span></span>     | <span data-ttu-id="24d58-154">Bekijk de toepassing van waaruit op de URL is geklikt.</span><span class="sxs-lookup"><span data-stu-id="24d58-154">See the application from which the URL was clicked.</span></span>        |
|  |  |

<span data-ttu-id="24d58-155">In de detailstabel u meer informatie zien over kliktijd en gebruikersinformatie.</span><span class="sxs-lookup"><span data-stu-id="24d58-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="24d58-156">Houd tot slot rekening met het rapport URL-beveiligingsstatus toont de functie Bescherming tegen ATP Safe Links, zodat alleen klanten die ATP Safe Links hebben ingeschakeld, gegevens in dit rapport zien.</span><span class="sxs-lookup"><span data-stu-id="24d58-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="24d58-157">Dit is een *trendrapport voor bescherming,* wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="24d58-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="24d58-158">Rapportage is hier niet in realtime beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="24d58-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="24d58-159">Voor realtime URL-klikgegevens blijft u URL-trace gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24d58-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="24d58-160">Rapport ATP-bestandstypen</span><span class="sxs-lookup"><span data-stu-id="24d58-160">ATP File Types report</span></span>

<span data-ttu-id="24d58-161">Het rapport **ATP-bestandstypen** toont u het type bestanden dat is gedetecteerd als kwaadaardig door [ATP-veilige bijlagen.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="24d58-161">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="24d58-162">Als u dit rapport wilt bekijken, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar **ATP-bestandstypen** **rapporten** \> **dashboard** \> .</span><span class="sxs-lookup"><span data-stu-id="24d58-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Rapport ATP-bestandstypen](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="24d58-164">Wanneer u over een bepaalde dag zweeft, u de uitsplitsing zien van typen schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-spam &amp; anti-malware bescherming in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="24d58-164">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Rapportgegevens van ATP-bestandstypen voor een dag](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="24d58-166">RAPPORT ATP-berichtdispositie</span><span class="sxs-lookup"><span data-stu-id="24d58-166">ATP Message Disposition report</span></span>

<span data-ttu-id="24d58-167">Het rapport **ATP-berichtdispositie** toont u de acties die zijn uitgevoerd voor e-mailberichten die zijn gedetecteerd als schadelijke inhoud.</span><span class="sxs-lookup"><span data-stu-id="24d58-167">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="24d58-168">Als u dit rapport wilt bekijken, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar Het **DASHBOARD** \> **ATP-berichtdispositie**van **rapporten** \> .</span><span class="sxs-lookup"><span data-stu-id="24d58-168">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Rapport over de dispositie van ATP-berichten](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="24d58-170">Wanneer u de boventoon over een balk in de grafiek zweeft, u zien welke acties zijn uitgevoerd voor gedetecteerde e-mail voor die dag.</span><span class="sxs-lookup"><span data-stu-id="24d58-170">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![GEGEVENS over atp-berichtdispositie voor een dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="24d58-172">Aanvullende rapporten om te bekijken</span><span class="sxs-lookup"><span data-stu-id="24d58-172">Additional reports to view</span></span>

<span data-ttu-id="24d58-173">Naast de atp-rapporten die in dit artikel worden beschreven, zijn er nog verschillende andere rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="24d58-173">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="24d58-174">Rapport(en)</span><span class="sxs-lookup"><span data-stu-id="24d58-174">Report(s)</span></span>  |<span data-ttu-id="24d58-175">Details</span><span class="sxs-lookup"><span data-stu-id="24d58-175">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="24d58-176">**Explorer-** of realtimedetecties (Office 365 ATP Plan **2-klanten** hebben Explorer; Klanten van Office 365 ATP Plan 1 hebben realtime detecties.)</span><span class="sxs-lookup"><span data-stu-id="24d58-176">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="24d58-177">Threat Explorer (en real-time detecties)</span><span class="sxs-lookup"><span data-stu-id="24d58-177">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="24d58-178">**E-mailbeveiligingsrapporten,** zoals een rapport Top afzenders en geadresseerden, een SpoofMailrapport en een rapport over spamdetecties.</span><span class="sxs-lookup"><span data-stu-id="24d58-178">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="24d58-179">E-mailbeveiligingsrapporten weergeven in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="24d58-179">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="24d58-180">**URL-trace voor ATP Safe Links** (dit is een rapport dat u genereert met PowerShell.) Dit rapport toont de resultaten van ATP Safe Links acties in de afgelopen zeven (7) dagen.</span><span class="sxs-lookup"><span data-stu-id="24d58-180">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="24d58-181">Get-UrlTrace-cmdlet-verwijzing</span><span class="sxs-lookup"><span data-stu-id="24d58-181">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="24d58-182">**EOP- en ATP-resultaten** (dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="24d58-182">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="24d58-183">Dit rapport bevat informatie, zoals Domein, Datum, Gebeurtenistype, Richting, Actie en Aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="24d58-183">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="24d58-184">Get-MailTrafficATPReport-cmdlet-verwijzing</span><span class="sxs-lookup"><span data-stu-id="24d58-184">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="24d58-185">**EOP- en ATP-detecties** (dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="24d58-185">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="24d58-186">Dit rapport bevat details over schadelijke bestanden of URL's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.</span><span class="sxs-lookup"><span data-stu-id="24d58-186">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="24d58-187">Get-MailDetailATPReport-cmdlet-verwijzing</span><span class="sxs-lookup"><span data-stu-id="24d58-187">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="24d58-188">Welke machtigingen zijn nodig om de ATP-rapporten te bekijken?</span><span class="sxs-lookup"><span data-stu-id="24d58-188">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="24d58-189">Als u de in dit artikel beschreven rapporten wilt bekijken en gebruiken, **moet u een geschikte rol hebben toegewezen voor zowel het Security &amp; Compliance Center als het Exchange-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="24d58-189">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="24d58-190">Voor het &amp; Security Compliance Center moet u een van de volgende rollen toegewezen hebben:</span><span class="sxs-lookup"><span data-stu-id="24d58-190">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="24d58-191">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="24d58-191">Organization Management</span></span>
    - <span data-ttu-id="24d58-192">Beveiligingsbeheerder (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ( ))</span><span class="sxs-lookup"><span data-stu-id="24d58-192">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="24d58-193">Beveiligingsoperator (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ( ))</span><span class="sxs-lookup"><span data-stu-id="24d58-193">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="24d58-194">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="24d58-194">Security Reader</span></span>

- <span data-ttu-id="24d58-195">Voor Exchange Online moet u een van de volgende rollen[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)hebben toegewezen in het Exchange-beheercentrum ( ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="24d58-195">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="24d58-196">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="24d58-196">Organization Management</span></span>
    - <span data-ttu-id="24d58-197">Organisatiebeheer alleen weergeven</span><span class="sxs-lookup"><span data-stu-id="24d58-197">View-only Organization Management</span></span>
    - <span data-ttu-id="24d58-198">Functie Alleen-weergaveontvangers</span><span class="sxs-lookup"><span data-stu-id="24d58-198">View-Only Recipients role</span></span>
    - <span data-ttu-id="24d58-199">Compliance Management</span><span class="sxs-lookup"><span data-stu-id="24d58-199">Compliance Management</span></span>

<span data-ttu-id="24d58-200">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="24d58-200">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="24d58-201">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="24d58-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="24d58-202">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24d58-202">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="24d58-203">Wat gebeurt er als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="24d58-203">What if the reports aren't showing data?</span></span>

<span data-ttu-id="24d58-204">Als u geen gegevens in uw ATP-rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="24d58-204">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="24d58-205">Uw organisatie moet beschikken [over atp-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) en beleid voor veilige [bevestigingen van ATP](set-up-atp-safe-attachments-policies.md) dat is gedefinieerd om de ATP-bescherming te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24d58-205">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="24d58-206">Zie ook [antispam- en anti-malwarebeveiliging in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="24d58-206">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="24d58-207">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="24d58-207">Related topics</span></span>

[<span data-ttu-id="24d58-208">Rapporten en inzichten in het &amp; Office 365 Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="24d58-208">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="24d58-209">Een planning maken voor een &amp; rapport in het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="24d58-209">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="24d58-210">Een aangepast rapport instellen en &amp; downloaden in het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="24d58-210">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="24d58-211">Machtigingen voor rollen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="24d58-211">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
  

