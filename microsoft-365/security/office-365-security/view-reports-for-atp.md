---
title: Rapporten weergeven voor Office 365 Advanced Threat Protection, malwarerapporten, phish-rapporten, gecompromitteerde accounts, URL-beveiligingstatus, bedreigingsrapportage, bedreigingen melden
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 1531a70439ae1c093ee472923696895eda0bc644
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809529"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="02adb-103">Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="02adb-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="02adb-104">Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) heeft en u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)beschikt, u verschillende ATP-rapporten gebruiken in het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="02adb-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="02adb-105">(Ga naar **Dashboard** **Rapporten** \> .)</span><span class="sxs-lookup"><span data-stu-id="02adb-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Het &amp; dashboard van het Security Compliance Center kan u helpen te zien waar Advanced Threat Protection werkt](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="02adb-107">ATP-rapporten bevatten de volgende:</span><span class="sxs-lookup"><span data-stu-id="02adb-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="02adb-108">Rapport over de status van bedreigingsbescherming</span><span class="sxs-lookup"><span data-stu-id="02adb-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="02adb-109">ATP-bestandstypenrapport</span><span class="sxs-lookup"><span data-stu-id="02adb-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="02adb-110">ATP Message Disposition rapport</span><span class="sxs-lookup"><span data-stu-id="02adb-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="02adb-111">[realtime detecties of Explorer](threat-explorer.md) (afhankelijk van of u Office 365 ATP-abonnement 1 of 2 hebt)</span><span class="sxs-lookup"><span data-stu-id="02adb-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="02adb-112">... [en meer](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="02adb-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="02adb-113">Lees dit artikel om een overzicht te krijgen van ATP-rapporten en hoe je ze gebruiken.</span><span class="sxs-lookup"><span data-stu-id="02adb-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="02adb-114">Rapport over de status van bedreigingsbescherming</span><span class="sxs-lookup"><span data-stu-id="02adb-114">Threat Protection Status report</span></span>

<span data-ttu-id="02adb-115">Het rapport **Status van bedreigingsbeveiliging** is een enkele weergave die informatie over schadelijke inhoud en schadelijke e-mail samenbrengt die is gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office [365 ATP.](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="02adb-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="02adb-116">Dit rapport is handig voor het bekijken van detecties in de loop van de tijd (tot 90 dagen) en stelt beveiligingsbeheerders in staat om trends te identificeren of te bepalen of het beleid aanpassingen nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="02adb-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="02adb-117">Het rapport biedt een geaggregeerd aantal unieke e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die werden geblokkeerd door de anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), en ATP-functies zoals [ATP Safe Links,](atp-safe-links.md) [ATP Safe Attachments](atp-safe-attachments.md), en [ATP anti-phishing mogelijkheden](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="02adb-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

<span data-ttu-id="02adb-118">Filters en uitsplitsingen van de informatie zorgen voor meer gedetailleerde indelingen van de informatie in dit rapport.</span><span class="sxs-lookup"><span data-stu-id="02adb-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="02adb-119">Specifiek, er is een 'break down by' menu opgenomen voor *E-mail > Phish* en *E-mail > Malware weergaven*.</span><span class="sxs-lookup"><span data-stu-id="02adb-119">Specifically, there is a 'break down by' menu included for *Email > Phish* and *Email > Malware views*.</span></span> <span data-ttu-id="02adb-120">Het zal breken de gegevens in:</span><span class="sxs-lookup"><span data-stu-id="02adb-120">It will break down the data into:</span></span>

| |  |
|---------|---------|
|<span data-ttu-id="02adb-121">Op detectietype</span><span class="sxs-lookup"><span data-stu-id="02adb-121">By detection type</span></span>    | <span data-ttu-id="02adb-122">Welk beleid heeft bijgedragen aan het opvangen van deze bedreigingen?</span><span class="sxs-lookup"><span data-stu-id="02adb-122">What policy helped catch these threats?</span></span>         |
|<span data-ttu-id="02adb-123">Door detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="02adb-123">By detection technology</span></span>     | <span data-ttu-id="02adb-124">Welke onderliggende Microsoft-technologie ving de dreiging?</span><span class="sxs-lookup"><span data-stu-id="02adb-124">What underlying Microsoft technology caught the threat?</span></span>        |
|<span data-ttu-id="02adb-125">Op leveringsstatus</span><span class="sxs-lookup"><span data-stu-id="02adb-125">By delivery status</span></span>     | <span data-ttu-id="02adb-126">Wat is er gebeurd met de e-mailberichten gedetecteerd als bedreigingen?</span><span class="sxs-lookup"><span data-stu-id="02adb-126">What happened to the email messages detected as threats?</span></span>         |
| | |

> [!TIP]
> <span data-ttu-id="02adb-127">Zowel de e-mail > Phish | Malwareweergaven hebben gedetailleerde uitsplitsingen voor de getoonde detectietechnologieën, met categorieën zoals *ATP-gegenereerde bestandsreputatie*, *Bestandsdetonatie*, *URL-ontploffing*, *Anti-spoof: DMARC-storing*, bijvoorbeeld nuttig bij het lokaliseren van precies welke functie uw organisatie ertoe bracht bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="02adb-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Threat Protection Status rapport dropdown met 'break down by'.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="02adb-129">Deze weergaven geven u de mogelijkheid om te exporteren, via een klik op de knop (in E-> Phish, E-mail > malware en content > malwareweergaven).</span><span class="sxs-lookup"><span data-stu-id="02adb-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="02adb-130">De geaggregeerde gegevens die naar uw computer worden geëxporteerd, kunnen worden geopend in Excel.</span><span class="sxs-lookup"><span data-stu-id="02adb-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![In deze afbeelding wordt Exporteren als optie weergegeven in het menu voor de weergave Malware, direct tussen Schema maken en Rapport aanvragen.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="02adb-132">De overzichts- en e-mailsweergaven geven informatie weer binnen enkele uren na verwerking in plaats van binnen 24 uur (vraag opnieuw.</span><span class="sxs-lookup"><span data-stu-id="02adb-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="02adb-133">hogere snelheden hier is een duidelijk signaal)!</span><span class="sxs-lookup"><span data-stu-id="02adb-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="02adb-134">Er is een rapport over de status van bedreigingsbeveiliging beschikbaar voor klanten die [Office 365 ATP](office-365-atp.md) of [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) hebben; De informatie die wordt weergegeven in het rapport Threat Protection Status voor ATP-klanten bevat echter waarschijnlijk andere gegevens dan wat EOP-klanten kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="02adb-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="02adb-135">Het rapport Status van bedreigingsstatus voor ATP-klanten bevat bijvoorbeeld informatie over schadelijke bestanden die zijn [gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="02adb-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="02adb-136">Dergelijke informatie is specifiek voor ATP, dus klanten die EOP hebben maar geen ATP, zien deze gegevens niet in hun rapport Threat Protection Status.</span><span class="sxs-lookup"><span data-stu-id="02adb-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="02adb-137">Als u het rapport Status voor bedreigingsbeveiliging wilt bekijken, gaat **Dashboard** \> u in het [Security &amp; Compliance Center](https://protection.office.com)naar De Status **bedreigingsbeveiliging** **van rapporten.** \></span><span class="sxs-lookup"><span data-stu-id="02adb-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP Threat Protection Status rapport](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="02adb-139">Als u een gedetailleerde status voor een dag wilt krijgen, moet u de grafiek doornemen.</span><span class="sxs-lookup"><span data-stu-id="02adb-139">To get detailed status for a day, hover over the graph.</span></span>
  
![ATP Threat Protection Status gegevens voor een dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="02adb-141">In het rapport Status bedreigingsbeveiliging worden standaard gegevens van de afgelopen zeven dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="02adb-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="02adb-142">U echter **filters** kiezen en het datumbereik wijzigen om gegevens tot 90 dagen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="02adb-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="02adb-143">(Als u een proefabonnement gebruikt, bent u mogelijk beperkt tot 30 dagen aan gegevens.)</span><span class="sxs-lookup"><span data-stu-id="02adb-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![ATP Threat Protection Status filters](../../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="02adb-145">U ook de **gegevens bekijken per** menu gebruiken om te wijzigen welke informatie in het rapport wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="02adb-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Weergaveopties voor het RAPPORT STATUS van ATP-dreigingsbescherming](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="02adb-147">Statusrapport URL-beveiliging</span><span class="sxs-lookup"><span data-stu-id="02adb-147">URL Protection Status report</span></span>

<span data-ttu-id="02adb-148">Dit rapport is gebaseerd op verzamelde gegevens en gedetecteerde bedreigingen per klik (terwijl de meeste andere e-mailbedreigingsgerelateerde rapporten per berichtgegevens zijn).</span><span class="sxs-lookup"><span data-stu-id="02adb-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="02adb-149">Dit rapport is ontworpen om bedreigingen weer te geven die afkomstig zijn van hyperlinks in e-mailberichten en documenten, per klik.</span><span class="sxs-lookup"><span data-stu-id="02adb-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="02adb-150">Er zijn twee weergaven:</span><span class="sxs-lookup"><span data-stu-id="02adb-150">There are two views:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="02adb-151">URL klik op beveiligingsactie</span><span class="sxs-lookup"><span data-stu-id="02adb-151">URL click protection action</span></span>   | <span data-ttu-id="02adb-152">Bekijk het aantal URL's dat is geblokkeerd, geblokkeerd maar overschreven met een doorklik door een gebruiker, die is overschreven met een doorklik door een gebruiker en is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="02adb-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>        |
|<span data-ttu-id="02adb-153">URL klik op toepassing</span><span class="sxs-lookup"><span data-stu-id="02adb-153">URL click by application</span></span>     | <span data-ttu-id="02adb-154">Zie de toepassing waarop op de URL is geklikt.</span><span class="sxs-lookup"><span data-stu-id="02adb-154">See the application from which the URL was clicked.</span></span>        |
|  |  |

<span data-ttu-id="02adb-155">In de tabel met details u meer informatie zien over kliktijd en gebruikersinformatie.</span><span class="sxs-lookup"><span data-stu-id="02adb-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="02adb-156">Houd er tot slot rekening mee dat in het rapport URL Protection Status de bescherming tegen de functie Veilige links van ATP wordt weergegeven, zodat alleen klanten die ATP Safe Links hebben ingeschakeld, gegevens in dit rapport zien.</span><span class="sxs-lookup"><span data-stu-id="02adb-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="02adb-157">Dit is een *trendrapport voor bescherming,* wat betekent dat gegevens trends in een grotere gegevensset weergeven.</span><span class="sxs-lookup"><span data-stu-id="02adb-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="02adb-158">Rapportage is hier niet in realtime beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="02adb-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="02adb-159">Voor realtime URL-klikgegevens u URL Trace blijven gebruiken.</span><span class="sxs-lookup"><span data-stu-id="02adb-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="02adb-160">ATP-bestandstypenrapport</span><span class="sxs-lookup"><span data-stu-id="02adb-160">ATP File Types report</span></span>

<span data-ttu-id="02adb-161">Het **rapport ATP-bestandstypen** toont u het type bestanden dat door [ATP Safe Attachments](atp-safe-attachments.md)als kwaadaardig is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="02adb-161">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="02adb-162">Ga naar **ATP-bestandstypen** **voor** \> **rapportendashboard** \> om dit rapport [ &amp; ](https://protection.office.com)weer te geven.</span><span class="sxs-lookup"><span data-stu-id="02adb-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP-bestandstypenrapport](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="02adb-164">Wanneer u een bepaalde dag zweeft, u de uitsplitsing zien van typen schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-spam &amp; anti-malware bescherming in Office 365.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="02adb-164">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Gegevens van ATP-bestandstypen voor een dag rapporteren](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="02adb-166">ATP Message Disposition rapport</span><span class="sxs-lookup"><span data-stu-id="02adb-166">ATP Message Disposition report</span></span>

<span data-ttu-id="02adb-167">Het **rapport ATP Message Disposition** toont u de acties die zijn uitgevoerd voor e-mailberichten die zijn gedetecteerd als met schadelijke inhoud.</span><span class="sxs-lookup"><span data-stu-id="02adb-167">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="02adb-168">Ga naar Het **DASHBOARD** \> **ATP-berichtdispositie** **van rapporten** \> om dit rapport [ &amp; ](https://protection.office.com)weer te geven.</span><span class="sxs-lookup"><span data-stu-id="02adb-168">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP-berichtdispositierapport](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="02adb-170">Wanneer u boven een balk in de grafiek zweeft, u zien welke acties zijn uitgevoerd voor gedetecteerde e-mail voor die dag.</span><span class="sxs-lookup"><span data-stu-id="02adb-170">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![Gegevens over het atp-berichtdispositie voor een dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="02adb-172">Aanvullende rapporten om te bekijken</span><span class="sxs-lookup"><span data-stu-id="02adb-172">Additional reports to view</span></span>

<span data-ttu-id="02adb-173">Naast de ATP-rapporten die in dit artikel worden beschreven, zijn er nog verschillende andere rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="02adb-173">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="02adb-174">Rapport(en)</span><span class="sxs-lookup"><span data-stu-id="02adb-174">Report(s)</span></span>  |<span data-ttu-id="02adb-175">Details</span><span class="sxs-lookup"><span data-stu-id="02adb-175">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="02adb-176">**Explorer-** of **realtime detecties** (Office 365 ATP Plan 2-klanten hebben Explorer; Office 365 ATP Plan 1-klanten hebben realtime detecties.)</span><span class="sxs-lookup"><span data-stu-id="02adb-176">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="02adb-177">Threat Explorer (en real-time detecties)</span><span class="sxs-lookup"><span data-stu-id="02adb-177">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="02adb-178">**Beveiligingsrapporten e-mailen,** zoals een rapport met topafzenders en geadresseerden, een rapport spoofmail en een rapport voor spamdetecties.</span><span class="sxs-lookup"><span data-stu-id="02adb-178">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="02adb-179">E-mailbeveiligingsrapporten weergeven in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="02adb-179">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="02adb-180">**ATP Safe Links URL trace** (Dit is een rapport dat u genereert met behulp van PowerShell.) Dit rapport toont de resultaten van ATP Safe Links acties in de afgelopen zeven (7) dagen.</span><span class="sxs-lookup"><span data-stu-id="02adb-180">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="02adb-181">Verwijzing naar get-UrlTrace-cmdlet</span><span class="sxs-lookup"><span data-stu-id="02adb-181">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="02adb-182">**EOP- en ATP-resultaten** (dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="02adb-182">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="02adb-183">Dit rapport bevat informatie, zoals Domein, Datum, Gebeurtenistype, Richting, Actie en Aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="02adb-183">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="02adb-184">Verwijzing naar de cmdlet van Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="02adb-184">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="02adb-185">**EOP- en ATP-detecties** (Dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="02adb-185">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="02adb-186">Dit rapport bevat details over schadelijke bestanden of URL's, phishingpogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.</span><span class="sxs-lookup"><span data-stu-id="02adb-186">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="02adb-187">Verwijzing naar get-MailDetailATPReport cmdlet</span><span class="sxs-lookup"><span data-stu-id="02adb-187">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="02adb-188">Welke machtigingen zijn nodig om de ATP-rapporten te bekijken?</span><span class="sxs-lookup"><span data-stu-id="02adb-188">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="02adb-189">Als u de in dit artikel beschreven rapporten wilt bekijken en gebruiken, moet u een geschikte rol hebben die is **toegewezen voor zowel het Security &amp; Compliance Center als het Exchange-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="02adb-189">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="02adb-190">Voor het &amp; Security Compliance Center moet u een van de volgende rollen hebben toegewezen:</span><span class="sxs-lookup"><span data-stu-id="02adb-190">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="02adb-191">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="02adb-191">Organization Management</span></span>
    - <span data-ttu-id="02adb-192">Beveiligingsbeheerder (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ())</span><span class="sxs-lookup"><span data-stu-id="02adb-192">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="02adb-193">Beveiligingsoperator (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ())</span><span class="sxs-lookup"><span data-stu-id="02adb-193">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="02adb-194">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="02adb-194">Security Reader</span></span>

- <span data-ttu-id="02adb-195">Voor Exchange Online moet u een van de volgende rollen[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)hebben toegewezen in het Exchange-beheercentrum ( ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="02adb-195">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="02adb-196">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="02adb-196">Organization Management</span></span>
    - <span data-ttu-id="02adb-197">Alleen-weergaveorganisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="02adb-197">View-only Organization Management</span></span>
    - <span data-ttu-id="02adb-198">Alleen-weergaveontvangers rol</span><span class="sxs-lookup"><span data-stu-id="02adb-198">View-Only Recipients role</span></span>
    - <span data-ttu-id="02adb-199">Compliance Management</span><span class="sxs-lookup"><span data-stu-id="02adb-199">Compliance Management</span></span>

<span data-ttu-id="02adb-200">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="02adb-200">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="02adb-201">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="02adb-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="02adb-202">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="02adb-202">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="02adb-203">Wat gebeurt er als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="02adb-203">What if the reports aren't showing data?</span></span>

<span data-ttu-id="02adb-204">Als u geen gegevens ziet in uw ATP-rapporten, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="02adb-204">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="02adb-205">Uw organisatie moet een [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) en [een ATP-beleid](set-up-atp-safe-attachments-policies.md) voor veilige bijlagen hebben dat is gedefinieerd om de ATP-beveiliging te kunnen invoeren.</span><span class="sxs-lookup"><span data-stu-id="02adb-205">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="02adb-206">Zie ook [anti-spam- en anti-malwarebescherming in Office 365.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="02adb-206">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="02adb-207">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="02adb-207">Related topics</span></span>

[<span data-ttu-id="02adb-208">Rapporten en inzichten in het &amp; Office 365 Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="02adb-208">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="02adb-209">Een planning maken voor een &amp; rapport in het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="02adb-209">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="02adb-210">Een aangepast rapport instellen en &amp; downloaden in het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="02adb-210">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="02adb-211">Rolmachtigingen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="02adb-211">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
  

