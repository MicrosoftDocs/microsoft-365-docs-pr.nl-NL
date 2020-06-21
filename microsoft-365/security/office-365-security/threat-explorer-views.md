---
title: Weergaven in Threat Explorer en realtime detecties
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over het gebruik van Threat Explorer en het rapport realtime detecties om bedreigingen te onderzoeken en erop te reageren in het Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae063cdcbd3d9b5d371e64513c90ff46503ec982
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819471"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="a9d74-103">Weergaven in Threat Explorer en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="a9d74-103">Views in Threat Explorer and real-time detections</span></span>

![Bedreigingsverkenner](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="a9d74-105">[Threat Explorer](threat-explorer.md) (en het real-time detectierapport) is een krachtig, bijna realtime hulpmiddel om security operations-teams te helpen bij het onderzoeken en reageren op bedreigingen in het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a9d74-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a9d74-106">Explorer (en het realtime detectierapport) geeft informatie weer over vermoedelijke malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsbedreigingen en -risico's voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a9d74-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="a9d74-107">Als u AtP-abonnement [(Advanced Threat Protection) (Advanced Threat Protection)](office-365-atp.md) (ATP) hebt, hebt u Explorer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="a9d74-108">Als u Office 365 ATP-abonnement 1 hebt, hebt u realtime detecties.</span><span class="sxs-lookup"><span data-stu-id="a9d74-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="a9d74-109">Wanneer u Explorer voor het eerst opent (of het realtime detectierapport), toont de standaardweergave detecties van e-mailmalware van de afgelopen 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="a9d74-110">Dit rapport kan ook ATP-detecties weergeven, zoals kwaadaardige URL's die zijn gedetecteerd door [veilige koppelingen](atp-safe-links.md)en schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="a9d74-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="a9d74-111">Dit rapport kan worden gewijzigd om gegevens van de afgelopen 30 dagen weer te geven (met een betaald ATP P2-abonnement).</span><span class="sxs-lookup"><span data-stu-id="a9d74-111">This report can be modified to show data for the past 30 days (with an ATP P2 paid subscription).</span></span> <span data-ttu-id="a9d74-112">Proefabonnementen bevatten alleen gegevens van de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-112">Trial subscriptions will include data for the past seven days only.</span></span>

|<span data-ttu-id="a9d74-113">Abonnement</span><span class="sxs-lookup"><span data-stu-id="a9d74-113">Subscription</span></span>  |<span data-ttu-id="a9d74-114">Utility</span><span class="sxs-lookup"><span data-stu-id="a9d74-114">Utility</span></span>  |<span data-ttu-id="a9d74-115">Dagen van gegevens</span><span class="sxs-lookup"><span data-stu-id="a9d74-115">Days of Data</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a9d74-116">ATP P1-proefversie</span><span class="sxs-lookup"><span data-stu-id="a9d74-116">ATP P1 trial</span></span>     | <span data-ttu-id="a9d74-117">Realtime detectie</span><span class="sxs-lookup"><span data-stu-id="a9d74-117">Real-time detections</span></span>        |   <span data-ttu-id="a9d74-118">7</span><span class="sxs-lookup"><span data-stu-id="a9d74-118">7</span></span>      |
|<span data-ttu-id="a9d74-119">ATP P1 betaald</span><span class="sxs-lookup"><span data-stu-id="a9d74-119">ATP P1 paid</span></span>     |   <span data-ttu-id="a9d74-120">Realtime detectie</span><span class="sxs-lookup"><span data-stu-id="a9d74-120">Real-time detections</span></span>      |    <span data-ttu-id="a9d74-121">30</span><span class="sxs-lookup"><span data-stu-id="a9d74-121">30</span></span>     |
|<span data-ttu-id="a9d74-122">ATP P1 betaald testen ATP P2 trial</span><span class="sxs-lookup"><span data-stu-id="a9d74-122">ATP P1 paid testing ATP P2 trial</span></span>     | <span data-ttu-id="a9d74-123">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="a9d74-123">Threat Explorer</span></span>   |   <span data-ttu-id="a9d74-124">7</span><span class="sxs-lookup"><span data-stu-id="a9d74-124">7</span></span>   |
|<span data-ttu-id="a9d74-125">ATP P2-proefversie</span><span class="sxs-lookup"><span data-stu-id="a9d74-125">ATP P2 trial</span></span>     |  <span data-ttu-id="a9d74-126">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="a9d74-126">Threat Explorer</span></span>       |     <span data-ttu-id="a9d74-127">7</span><span class="sxs-lookup"><span data-stu-id="a9d74-127">7</span></span>    |
|<span data-ttu-id="a9d74-128">ATP P2 betaald</span><span class="sxs-lookup"><span data-stu-id="a9d74-128">ATP P2 paid</span></span>     |     <span data-ttu-id="a9d74-129">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="a9d74-129">Threat Explorer</span></span>    |  <span data-ttu-id="a9d74-130">30</span><span class="sxs-lookup"><span data-stu-id="a9d74-130">30</span></span>       |

<span data-ttu-id="a9d74-131">Gebruik het menu **Weergave** om te wijzigen welke informatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a9d74-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="a9d74-132">Met tooltips u bepalen welke weergave u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a9d74-132">Tooltips help you determine which view to use.</span></span>
  
![Menu Weergave bedreigingverkenner](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="a9d74-134">Zodra u een weergave hebt geselecteerd, u filters toepassen en query's instellen om verdere analyses uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a9d74-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="a9d74-135">De volgende secties geven een kort overzicht van de verschillende weergaven die beschikbaar zijn in Explorer (of real-time detecties).</span><span class="sxs-lookup"><span data-stu-id="a9d74-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="a9d74-136">E-mail > malware</span><span class="sxs-lookup"><span data-stu-id="a9d74-136">Email > Malware</span></span>

<span data-ttu-id="a9d74-137">Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtime detecties)  >  **E-mailmalware**weergeven.  >  **Malware**</span><span class="sxs-lookup"><span data-stu-id="a9d74-137">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="a9d74-138">Deze weergave toont informatie over e-mailberichten die zijn geïdentificeerd als malware.</span><span class="sxs-lookup"><span data-stu-id="a9d74-138">This view shows information about email messages that were identified as containing malware.</span></span>  

![Gegevens weergeven over e-mail die als malware is geïdentificeerd](../../media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="a9d74-140">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a9d74-141">Gebruik deze lijst om gegevens van afzender, geadresseerden, afzenderdomein, onderwerp, detectietechnologie, beveiligingsstatus en meer weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a9d74-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="a9d74-142">Als u bijvoorbeeld wilt zien welke acties zijn uitgevoerd op gedetecteerde e-mailberichten, kiest u **De status Beveiliging** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a9d74-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="a9d74-143">Selecteer een optie en klik op de knop Vernieuwen om dat filter toe te passen op uw rapport.</span><span class="sxs-lookup"><span data-stu-id="a9d74-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opties voor bedreigingsbeveiligingsstatus voor Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="a9d74-145">Bekijk onder de grafiek meer details over specifieke berichten.</span><span class="sxs-lookup"><span data-stu-id="a9d74-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="a9d74-146">Wanneer u een item in de lijst selecteert, wordt een fly-out-deelvenster geopend, waar u meer informatie geven over het item dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a9d74-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Threat Explorer met flyout geopend](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="a9d74-148">E-mail > Phish</span><span class="sxs-lookup"><span data-stu-id="a9d74-148">Email > Phish</span></span>

<span data-ttu-id="a9d74-149">Als u dit rapport wilt weergeven in Explorer (of realtimedetecties), kiest **u**  >  **E-mail**  >  **Phish**weergeven.</span><span class="sxs-lookup"><span data-stu-id="a9d74-149">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="a9d74-150">In deze weergave worden e-mailberichten weergegeven die zijn geïdentificeerd als phishingpogingen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-150">This view shows email messages identified as phishing attempts.</span></span>  

![Gegevens weergeven over e-mail die is geïdentificeerd als phishingpogingen](../../media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="a9d74-152">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a9d74-153">Gebruik deze lijst om gegevens weer te geven per afzender, geadresseerden, afzenderdomein, IP-adres voor afzenders, URL-domein, klik op vonnis en meer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="a9d74-154">Als u bijvoorbeeld wilt zien welke acties zijn ondernomen wanneer mensen op URL's hebben geklikt die zijn geïdentificeerd als phishingpogingen, kiest u **Klik op verdict** in de lijst, selecteert u een of meer opties en klikt u op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klik op verdict opties voor het Phish rapport](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="a9d74-156">Bekijk onder de grafiek meer details over specifieke berichten, URL-klikken, URL's en e-mailoorsprong.</span><span class="sxs-lookup"><span data-stu-id="a9d74-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![URL's gedetecteerd als phish in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="a9d74-158">Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een fly-out-deelvenster geopend, waar u meer informatie krijgen over het item dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a9d74-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Details over een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="a9d74-160">E->-inzendingen</span><span class="sxs-lookup"><span data-stu-id="a9d74-160">Email > Submissions</span></span>

<span data-ttu-id="a9d74-161">Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtimedetecties)  >  **E-mailinzendingen**  >  **weergeven**.</span><span class="sxs-lookup"><span data-stu-id="a9d74-161">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="a9d74-162">Deze weergave toont e-mail die gebruikers hebben gerapporteerd als ongewenste, niet ongewenste e-mail of phishing.</span><span class="sxs-lookup"><span data-stu-id="a9d74-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![E-mailberichten gerapporteerd door gebruikers](../../media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="a9d74-164">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="a9d74-165">Gebruik deze lijst om informatie te bekijken per afzender, ontvangers, rapporttype (de vaststelling van de gebruiker dat de e-mail ongewenste e-mail was, niet ongewenste of phish), en meer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="a9d74-166">Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die als phishingpogingen zijn gerapporteerd, klikt u op **Sender**  >  **type afzenderrapport,** selecteert u **Phish**en klikt u op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish geselecteerd voor filter Rapporttype](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="a9d74-168">Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, het IP-adres van de afzender, de gebruiker die het bericht als ongewenste, niet ongewenste of phish, en meer heeft gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="a9d74-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![Berichten die zijn gerapporteerd als phishingpogingen](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="a9d74-170">Selecteer een item in de lijst om aanvullende details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a9d74-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="a9d74-171">E-> alle e-mail</span><span class="sxs-lookup"><span data-stu-id="a9d74-171">Email > All email</span></span>

<span data-ttu-id="a9d74-172">Als u dit rapport wilt weergeven, kiest **u**in Explorer De optie  >  **E-mail**alle  >  **e-mail**weergeven .</span><span class="sxs-lookup"><span data-stu-id="a9d74-172">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="a9d74-173">Deze weergave toont een all-up weergave van e-mailactiviteiten, inclusief e-mail die als kwaadaardig is geïdentificeerd als gevolg van phishing of malware, evenals alle niet-schadelijke e-mail (normale e-mail, spam en bulkmail).</span><span class="sxs-lookup"><span data-stu-id="a9d74-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="a9d74-174">Als u een foutmelding krijgt die te veel gegevens leest **om weer te geven,** voegt u een filter toe en verkleint u indien nodig het datumbereik dat u bekijkt.</span><span class="sxs-lookup"><span data-stu-id="a9d74-174">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="a9d74-175">Als u een filter wilt toepassen, kiest u **Afzender,** selecteert u een item in de lijst en klikt u op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-175">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="a9d74-176">In ons voorbeeld **gebruikten** we Detectietechnologie als filter (er zijn verschillende opties beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="a9d74-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="a9d74-177">Bekijk informatie per afzender, afzenderdomein, ontvangers, onderwerp, bestandsnaam van bijlagen, malwarefamilie, beveiligingsstatus (acties die zijn uitgevoerd door uw functies en beleid voor bedreigingsbescherming in Office 365), detectietechnologie (hoe de malware is gedetecteerd) en meer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Gegevens over gedetecteerde e-mail weergeven door detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="a9d74-179">Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, ontvanger, afzender, status, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="a9d74-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="a9d74-180">Content > Malware</span><span class="sxs-lookup"><span data-stu-id="a9d74-180">Content > Malware</span></span>

<span data-ttu-id="a9d74-181">Als u dit rapport wilt bekijken, kiest u **View**in Explorer (of realtime detecties) De optie  >  **Inhoudsmalware**  >  **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="a9d74-181">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="a9d74-182">In deze weergave worden bestanden weergegeven die door Office 365 Advanced Threat Protection als kwaadaardig zijn geïdentificeerd [in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a9d74-182">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="a9d74-183">Bekijk informatie per malwarefamilie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of Teams).</span><span class="sxs-lookup"><span data-stu-id="a9d74-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Gegevens over gedetecteerde malware weergeven](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="a9d74-185">Bekijk onder de grafiek meer details over specifieke bestanden, zoals bestandsnaam van bijlagen, werkbelasting, bestandsgrootte, die het bestand voor het laatst hebben gewijzigd en meer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="a9d74-186">Klik-naar-filter mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="a9d74-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="a9d74-187">Met Explorer (en realtime detecties) u met één klik een filter toepassen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="a9d74-188">Klik op een item in de legenda en dat item wordt een filter voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="a9d74-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="a9d74-189">Stel dat we kijken naar de malwareweergave in Explorer:</span><span class="sxs-lookup"><span data-stu-id="a9d74-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Ga naar Threat management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="a9d74-191">Als u op **ATP Detonation** in deze grafiek klikt, resulteert dit in een weergave als deze:</span><span class="sxs-lookup"><span data-stu-id="a9d74-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorer gefilterd om alleen ATP-detonatieresultaten weer te geven](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="a9d74-193">In deze weergave kijken we nu naar gegevens voor bestanden die zijn ontploft door [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="a9d74-193">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="a9d74-194">Onder de grafiek kunnen we details zien over specifieke e-mailberichten met bijlagen die zijn gedetecteerd door ATP Safe Attachments.</span><span class="sxs-lookup"><span data-stu-id="a9d74-194">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Specifieke details over e-mailberichten met gedetecteerde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="a9d74-196">Als u een of meer items selecteert, wordt het menu **Acties** geactiveerd, waarin verschillende opties worden aangeboden waaruit u kiezen voor het geselecteerde item(s).</span><span class="sxs-lookup"><span data-stu-id="a9d74-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Als u een item selecteert, wordt het menu Acties geactiveerd](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="a9d74-198">De mogelijkheid om in een klik te filteren en naar specifieke details te navigeren, kan u veel tijd besparen bij het onderzoeken van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="a9d74-199">Query's en filters</span><span class="sxs-lookup"><span data-stu-id="a9d74-199">Queries and filters</span></span>

<span data-ttu-id="a9d74-200">Explorer (evenals de real-time detecties rapport) heeft een aantal krachtige filters en query's mogelijkheden die u in staat stellen om te boren in details, zoals top gerichte gebruikers, top malware families, detectie technologie en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="a9d74-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="a9d74-201">Elk type rapport biedt verschillende manieren om gegevens te bekijken en te verkennen.</span><span class="sxs-lookup"><span data-stu-id="a9d74-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9d74-202">Gebruik geen jokertekens, zoals een sterretje of een vraagteken, in de querybalk voor Explorer (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="a9d74-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="a9d74-203">Wanneer u in het **veld Onderwerp** zoekt naar e-mailberichten, voert Explorer (of realtime detecties) gedeeltelijke matching uit en levert resultaten op die vergelijkbaar zijn met een zoekopdracht met een wildcard.</span><span class="sxs-lookup"><span data-stu-id="a9d74-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
