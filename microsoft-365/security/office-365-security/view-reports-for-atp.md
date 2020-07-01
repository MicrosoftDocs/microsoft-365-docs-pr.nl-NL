---
title: Rapporten voor geavanceerde bedreigingsbeveiliging weergeven
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
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
description: Rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365 zoeken en gebruiken in het Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c71bef11e574593d821b992f3a5037dbf127d5d2
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936993"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="778a4-103">Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="778a4-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="778a4-104">Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) heeft en u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)beschikt, u verschillende ATP-rapporten gebruiken in het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="778a4-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="778a4-105">(Ga naar **Rapporten** \> **Dashboard**.)</span><span class="sxs-lookup"><span data-stu-id="778a4-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![Het dashboard van het Security &amp; Compliance Center kan u helpen te zien waar Geavanceerde bedreigingsbeveiliging werkt](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="778a4-107">ATP-rapporten bevatten het volgende:</span><span class="sxs-lookup"><span data-stu-id="778a4-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="778a4-108">Statusrapport risicobeveiliging</span><span class="sxs-lookup"><span data-stu-id="778a4-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="778a4-109">ATP-bestandstyperapport</span><span class="sxs-lookup"><span data-stu-id="778a4-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="778a4-110">ATP-rapport over berichtverwerking</span><span class="sxs-lookup"><span data-stu-id="778a4-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="778a4-111">[real-time detecties of Explorer](threat-explorer.md) (afhankelijk van of u Office 365 ATP Plan 1 of 2 hebt)</span><span class="sxs-lookup"><span data-stu-id="778a4-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="778a4-112">... [en meer.](#additional-reports-to-view)</span><span class="sxs-lookup"><span data-stu-id="778a4-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="778a4-113">Lees dit artikel voor een overzicht van ATP-rapporten en hoe ze te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="778a4-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="778a4-114">Statusrapport risicobeveiliging</span><span class="sxs-lookup"><span data-stu-id="778a4-114">Threat Protection Status report</span></span>

<span data-ttu-id="778a4-115">Het **rapport bedreigingsbeveiligingsstatus** is één weergave die informatie over schadelijke inhoud en schadelijke e-mail samenbrengt die is gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office [365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="778a4-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="778a4-116">Dit rapport is handig voor het bekijken van detecties in de loop van de tijd (tot 90 dagen) en stelt beveiligingsbeheerders in staat om trends te identificeren of te bepalen of beleid aanpassingen nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="778a4-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="778a4-117">Het rapport biedt een geaggregeerd aantal unieke e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die werden geblokkeerd door de anti-malware-engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md)en ATP-functies zoals [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md)en [ATP-anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="778a4-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="778a4-118">Filters en uitsplitsingen van de informatie zorgen voor meer gedetailleerde categorisaties van de informatie in dit rapport.</span><span class="sxs-lookup"><span data-stu-id="778a4-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="778a4-119">Specifiek, er is een 'break down by' menu opgenomen voor **E-mail** \> **Phish** en **E-mail** \> **Malware weergaven**.</span><span class="sxs-lookup"><span data-stu-id="778a4-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="778a4-120">Het zal de gegevens opsplitsen in:</span><span class="sxs-lookup"><span data-stu-id="778a4-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="778a4-121">Op beleidstype</span><span class="sxs-lookup"><span data-stu-id="778a4-121">By policy type</span></span>|<span data-ttu-id="778a4-122">Welk beleid heeft geholpen deze bedreigingen op te vangen?</span><span class="sxs-lookup"><span data-stu-id="778a4-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="778a4-123">Door detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="778a4-123">By detection technology</span></span>|<span data-ttu-id="778a4-124">Welke onderliggende Microsoft-technologie ving de dreiging?</span><span class="sxs-lookup"><span data-stu-id="778a4-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="778a4-125">Door leveringsstatus</span><span class="sxs-lookup"><span data-stu-id="778a4-125">By delivery status</span></span>|<span data-ttu-id="778a4-126">Wat was de uiteindelijke leveringsstatus van e-mailberichten die als bedreigingen werden gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="778a4-126">What was the final delivery status of email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="778a4-127">Zowel de e-mail > Phish | Malware weergaven hebben gedetailleerde storingen voor de detectietechnologieën getoond, met categorieën zoals *ATP-gegenereerde bestand reputatie*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC mislukking*, bijvoorbeeld, nuttig bij het lokaliseren precies welke functie leidde uw organisatie om bedreigingen te vangen.</span><span class="sxs-lookup"><span data-stu-id="778a4-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Threat Protection Status rapport dropdown toont 'break down by'.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="778a4-129">Deze weergaven geven u de mogelijkheid om te exporteren, via een knop klik (in **E-mail** \> **Phish**, **E-mail** \> **Malware**, en **Content** \> **Malware** weergaven).</span><span class="sxs-lookup"><span data-stu-id="778a4-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="778a4-130">De geaggregeerde gegevens die naar uw computer worden geëxporteerd, kunnen worden geopend in Excel.</span><span class="sxs-lookup"><span data-stu-id="778a4-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Deze afbeelding toont Exporteren als een optie in het menu voor de malwareweergave, precies tussen Planning maken en Aanvraagrapport.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

> [!NOTE]
> <span data-ttu-id="778a4-132">Het maximum aantal inzendingen dat kan worden geëxporteerd voor **Phish** en **Malware** is iets minder dan 10000.</span><span class="sxs-lookup"><span data-stu-id="778a4-132">The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="778a4-133">Als u een weergave exporteert, worden alleen de meest recente 10000 vermeldingen geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="778a4-133">If you export a view, only the most recent 10000 entries are exported.</span></span> <span data-ttu-id="778a4-134">Op de geëxporteerde gegevens vertegenwoordigt de kolom _berichttelling_ het aantal berichten dat wordt gedetecteerd door de detectietechnologie en het beleidstype.</span><span class="sxs-lookup"><span data-stu-id="778a4-134">On the exported data, the _message count_ column represents the number of messages detected by the detection technology and policy type.</span></span>    

<span data-ttu-id="778a4-135">De weergaven Overzicht en E-mails geven informatie weer binnen enkele uren na verwerking in plaats van in 24 uur (vraag opnieuw.</span><span class="sxs-lookup"><span data-stu-id="778a4-135">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="778a4-136">hogere snelheden hier is een duidelijk signaal)!</span><span class="sxs-lookup"><span data-stu-id="778a4-136">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="778a4-137">Een rapport over de status van bedreigingsbescherming is beschikbaar voor klanten die [office 365 ATP](office-365-atp.md) of [Exchange Online Protection](exchange-online-protection-overview.md)(EOP) hebben; De informatie die wordt weergegeven in het rapport Bedreigingsstatus voor ATP-klanten zal echter waarschijnlijk andere gegevens bevatten dan wat EOP-klanten kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="778a4-137">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-overview.md)) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="778a4-138">Het rapport Bedreigingsbeveiligingsstatus voor ATP-klanten bevat bijvoorbeeld informatie over [schadelijke bestanden die zijn gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="778a4-138">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="778a4-139">Dergelijke informatie is specifiek voor ATP, dus klanten die EOP hebben maar geen ATP zien deze gegevens niet in hun Threat Protection Status rapport.</span><span class="sxs-lookup"><span data-stu-id="778a4-139">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="778a4-140">Als u het rapport bedreigingsbeveiliging wilt bekijken, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar De status van **Reports** \> **Dashboard** \> **bedreigingsbeveiliging**rapporten.</span><span class="sxs-lookup"><span data-stu-id="778a4-140">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![ATP Threat Protection Status rapport ATP Threat Protection Status report ATP Threat Protection Status report ATP](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="778a4-142">Als u een dag van een dag een gedetailleerde status wilt krijgen, houdt u de muisaanwijzer boven de grafiek.</span><span class="sxs-lookup"><span data-stu-id="778a4-142">To get detailed status for a day, hover over the graph.</span></span>

![ATP Threat Protection Status gegevens voor een dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="778a4-144">Standaard worden in het rapport Bedreigingsbeveiligingsstatus gegevens van de afgelopen zeven dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="778a4-144">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="778a4-145">U filters **echter** kiezen en het datumbereik wijzigen om gegevens maximaal 90 dagen weer te geven voor de totale weergave en 30 dagen voor de detailweergave.</span><span class="sxs-lookup"><span data-stu-id="778a4-145">However, you can choose **Filters** and change the date range to view data for up to 90 days for the aggregate view and 30 days for the detail view.</span></span> <span data-ttu-id="778a4-146">(Als u een proefabonnement gebruikt, bent u mogelijk beperkt tot 30 dagen aan gegevens.)</span><span class="sxs-lookup"><span data-stu-id="778a4-146">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![ATP-statusstatusfilters voor bedreigingsbeveiliging](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="778a4-148">U ook de **gegevens weergeven per** menu gebruiken om te wijzigen welke informatie in het rapport wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="778a4-148">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Opties voor ATP-statusstatusbeveiligingsstatus weergeven](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="778a4-150">Rapport URL-beveiligingsstatus</span><span class="sxs-lookup"><span data-stu-id="778a4-150">URL Protection Status report</span></span>

<span data-ttu-id="778a4-151">Dit rapport is gebaseerd op verzamelde gegevens en bedreigingen die per klik worden gedetecteerd (terwijl de meeste andere rapporten met e-mailbedreiging per bericht zijn).</span><span class="sxs-lookup"><span data-stu-id="778a4-151">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="778a4-152">Dit rapport is ontworpen om bedreigingen weer te geven die afkomstig zijn van hyperlinks in e-mailberichten en documenten, per klik.</span><span class="sxs-lookup"><span data-stu-id="778a4-152">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="778a4-153">Er zijn twee weergaven:</span><span class="sxs-lookup"><span data-stu-id="778a4-153">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="778a4-154">URL-klikbeveiligingsactie</span><span class="sxs-lookup"><span data-stu-id="778a4-154">URL click protection action</span></span>|<span data-ttu-id="778a4-155">Bekijk het aantal URL's dat door een gebruiker is geblokkeerd, geblokkeerd maar overschreven met een doorklik door een gebruiker, wordt overschreven met een doorklik door een gebruiker en is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="778a4-155">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="778a4-156">URL klik op toepassing</span><span class="sxs-lookup"><span data-stu-id="778a4-156">URL click by application</span></span>|<span data-ttu-id="778a4-157">Bekijk de toepassing van waaruit de URL is geklikt.</span><span class="sxs-lookup"><span data-stu-id="778a4-157">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="778a4-158">In de tabel Details u meer informatie zien over kliktijd en gebruikersinformatie.</span><span class="sxs-lookup"><span data-stu-id="778a4-158">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="778a4-159">Tot slot, houd er rekening mee dat het URL-beveiligingsstatusrapport de beveiligingsfunctie van ATP-apparaten weergeeft, zodat alleen klanten die ATP Safe Links hebben ingeschakeld, gegevens in dit rapport worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="778a4-159">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="778a4-160">Dit is een *beveiligingstrendrapport,* wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="778a4-160">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="778a4-161">Als gevolg hiervan zijn de gegevens in de geaggregeerde weergave hier niet in realtime beschikbaar, maar de gegevens in de tabelweergave details zijn, dus u een lichte discrepantie tussen de twee weergaven zien.</span><span class="sxs-lookup"><span data-stu-id="778a4-161">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="778a4-162">ATP-bestandstyperapport</span><span class="sxs-lookup"><span data-stu-id="778a4-162">ATP File Types report</span></span>

<span data-ttu-id="778a4-163">Het rapport **ATP-bestandstypen** toont u het type bestanden dat door [ATP Safe Attachments](atp-safe-attachments.md)als kwaadaardig is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="778a4-163">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="778a4-164">Als u dit rapport wilt weergeven, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar **ATP-bestandstypen** \> **rapportendashboard** \> **.**</span><span class="sxs-lookup"><span data-stu-id="778a4-164">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![ATP-bestandstyperapport](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="778a4-166">Wanneer u gedurende een bepaalde dag zweeft, u de verdeling zien van soorten schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-spam &amp; anti-malware bescherming.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="778a4-166">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span> <span data-ttu-id="778a4-167">De totale weergave van het rapport maakt het mogelijk om 90 dagen te filteren, terwijl de detailweergave slechts tien dagen filtering mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="778a4-167">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span> 
  
![Rapportgegevens van ATP-bestandstypen voor een dag rapporteren](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="778a4-169">ATP-rapport over berichtverwerking</span><span class="sxs-lookup"><span data-stu-id="778a4-169">ATP Message Disposition report</span></span>

<span data-ttu-id="778a4-170">Het **ATP-bericht dispositie** rapport toont u de acties die zijn genomen voor e-mailberichten die zijn gedetecteerd als met kwaadaardige inhoud.</span><span class="sxs-lookup"><span data-stu-id="778a4-170">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="778a4-171">Als u dit rapport wilt weergeven, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar De **Reports** \> **Dashboard** \> **atp-berichtweergave**van rapportendashboard .</span><span class="sxs-lookup"><span data-stu-id="778a4-171">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![ATP-bericht dispositie rapport](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="778a4-173">Wanneer u boven een balk in de grafiek zweeft, u zien welke acties zijn uitgevoerd voor gedetecteerde e-mail voor die dag.</span><span class="sxs-lookup"><span data-stu-id="778a4-173">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![Atp-berichtdispositierapportgegevens voor een dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="778a4-175">Aanvullende rapporten om weer te geven</span><span class="sxs-lookup"><span data-stu-id="778a4-175">Additional reports to view</span></span>

<span data-ttu-id="778a4-176">Naast de ATP-rapporten die in dit artikel worden beschreven, zijn er nog verschillende rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="778a4-176">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="778a4-177">**Rapport(en)**</span><span class="sxs-lookup"><span data-stu-id="778a4-177">**Report(s)**</span></span>|<span data-ttu-id="778a4-178">**Details**</span><span class="sxs-lookup"><span data-stu-id="778a4-178">**Details**</span></span>|
|<span data-ttu-id="778a4-179">**Explorer-** of realtime detecties :(Office 365 ATP Plan **2-klanten**hebben Explorer; Office 365 ATP Plan 1-klanten hebben realtime detecties.)</span><span class="sxs-lookup"><span data-stu-id="778a4-179">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="778a4-180">Bedreigingsverkenner (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="778a4-180">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="778a4-181">**E-mailbeveiligingsrapporten,** zoals een rapport Over afzenders en geadresseerden, een spoofberichtrapport en een rapport over spamdetecties.</span><span class="sxs-lookup"><span data-stu-id="778a4-181">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="778a4-182">E-mailbeveiligingsrapporten weergeven in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="778a4-182">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="778a4-183">**URL-tracering van ATP Safe**Links:(Dit is een rapport dat u genereert met PowerShell.) Dit rapport toont de resultaten van ATP Safe Links acties in de afgelopen zeven (7) dagen.</span><span class="sxs-lookup"><span data-stu-id="778a4-183">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="778a4-184">Verwijzing naar Get-UrlTrace-cmdlet</span><span class="sxs-lookup"><span data-stu-id="778a4-184">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="778a4-185">**EOP- en ATP-resultaten**: (Dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="778a4-185">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="778a4-186">Dit rapport bevat informatie, zoals Domein, Datum, Gebeurtenistype, Richting, Actie en Aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="778a4-186">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="778a4-187">Get-MailTrafficATPReport cmdlet referentie</span><span class="sxs-lookup"><span data-stu-id="778a4-187">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="778a4-188">**EOP- en ATP-detecties**: (Dit is een aangepast rapport dat u genereert met PowerShell).</span><span class="sxs-lookup"><span data-stu-id="778a4-188">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="778a4-189">Dit rapport bevat details over schadelijke bestanden of URL's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.</span><span class="sxs-lookup"><span data-stu-id="778a4-189">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="778a4-190">Get-MailDetailATPReport cmdlet referentie</span><span class="sxs-lookup"><span data-stu-id="778a4-190">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="778a4-191">Welke machtigingen zijn nodig om de ATP-rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="778a4-191">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="778a4-192">Als u de in dit artikel beschreven rapporten wilt weergeven en gebruiken, **moet u een passende rol hebben toegewezen voor zowel het Security Compliance Center als het &amp; Exchange-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="778a4-192">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="778a4-193">Voor het Security &amp; Compliance Center moet u een van de volgende rollen toegewezen hebben:</span><span class="sxs-lookup"><span data-stu-id="778a4-193">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="778a4-194">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="778a4-194">Organization Management</span></span>
  - <span data-ttu-id="778a4-195">Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="778a4-195">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="778a4-196">Beveiligingsoperator (dit kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="778a4-196">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="778a4-197">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="778a4-197">Security Reader</span></span>

- <span data-ttu-id="778a4-198">Voor Exchange Online moet u een van de volgende rollen hebben toegewezen in het Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="778a4-198">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="778a4-199">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="778a4-199">Organization Management</span></span>
  - <span data-ttu-id="778a4-200">Alleen-weergeven organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="778a4-200">View-only Organization Management</span></span>
  - <span data-ttu-id="778a4-201">Rol alleen weergeven ontvangers</span><span class="sxs-lookup"><span data-stu-id="778a4-201">View-Only Recipients role</span></span>
  - <span data-ttu-id="778a4-202">Compliance Management</span><span class="sxs-lookup"><span data-stu-id="778a4-202">Compliance Management</span></span>

<span data-ttu-id="778a4-203">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="778a4-203">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="778a4-204">Machtigingen in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="778a4-204">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="778a4-205">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="778a4-205">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="778a4-206">Wat als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="778a4-206">What if the reports aren't showing data?</span></span>

<span data-ttu-id="778a4-207">Als u geen gegevens ziet in uw ATP-rapporten, controleert u dubbel of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="778a4-207">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="778a4-208">Uw organisatie moet [atp-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) en [atp-veilige bijlagen hebben](set-up-atp-safe-attachments-policies.md) gedefinieerd om atp-beveiliging op zijn plaats te krijgen.</span><span class="sxs-lookup"><span data-stu-id="778a4-208">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="778a4-209">Zie ook [anti-spam en anti-malware bescherming in Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="778a4-209">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="778a4-210">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="778a4-210">Related topics</span></span>

[<span data-ttu-id="778a4-211">Rapporten en inzichten in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="778a4-211">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="778a4-212">Rolmachtigingen (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="778a4-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
