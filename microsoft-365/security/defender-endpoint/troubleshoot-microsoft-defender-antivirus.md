---
title: Microsoft Defender AV-gebeurtenis-IDs en foutcodes
description: Zoek de oorzaken en oplossingen voor Microsoft Defender Antivirus gebeurtenis-ID's en fouten
keywords: gebeurtenis, foutcode, siem, logboekregistratie, probleemoplossing, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275346"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="8fc3a-104">Gebeurtenislogboeken en foutcodes bekijken voor het oplossen van problemen met Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8fc3a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8fc3a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8fc3a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8fc3a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8fc3a-107">Als u een probleem ondervindt met Microsoft Defender Antivirus, kunt u in de tabellen in dit onderwerp zoeken naar een overeenkomend probleem en een mogelijke oplossing.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="8fc3a-108">De lijst met tabellen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-108">The tables list:</span></span>

- <span data-ttu-id="8fc3a-109">[Microsoft Defender Antivirus gebeurtenis-ID's](#windows-defender-av-ids) (deze zijn van toepassing op zowel Windows 10 als Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="8fc3a-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="8fc3a-110">Microsoft Defender Antivirus clientfoutcodes</span><span class="sxs-lookup"><span data-stu-id="8fc3a-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="8fc3a-111">Interne Microsoft Defender Antivirus clientfoutcodes (gebruikt door Microsoft tijdens ontwikkeling en testen)</span><span class="sxs-lookup"><span data-stu-id="8fc3a-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="8fc3a-112">U kunt ook naar de demowebsite [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen dat de volgende functies werken:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="8fc3a-113">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="8fc3a-114">Snel leren (inclusief Blok op het eerste gezicht)</span><span class="sxs-lookup"><span data-stu-id="8fc3a-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="8fc3a-115">Mogelijk ongewenste blokkering van toepassingen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="8fc3a-116">Microsoft Defender Antivirus gebeurtenis-IDs</span><span class="sxs-lookup"><span data-stu-id="8fc3a-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="8fc3a-117">Microsoft Defender Antivirus records gebeurtenis-ID's in het Windows gebeurtenislogboek.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="8fc3a-118">U kunt het gebeurtenislogboek rechtstreeks bekijken of als u een hulpprogramma voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) van derden hebt, kunt u ook [Microsoft Defender Antivirus clientgebeurtenis-ID's](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) gebruiken om specifieke gebeurtenissen en fouten van uw eindpunten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="8fc3a-119">De tabel in deze sectie bevat de belangrijkste Microsoft Defender Antivirus gebeurtenis-ID's en biedt, indien mogelijk, voorgestelde oplossingen om de fout op te lossen of op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="8fc3a-120">Een gebeurtenis Microsoft Defender Antivirus weergeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="8fc3a-121">**Gebeurtenisviewer openen.**</span><span class="sxs-lookup"><span data-stu-id="8fc3a-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="8fc3a-122">Vouw in de consolestructuur **Toepassingen en Services-logboeken** uit, vervolgens **Microsoft**, Windows **en** **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="8fc3a-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="8fc3a-123">Dubbelklik op **Operationeel.**</span><span class="sxs-lookup"><span data-stu-id="8fc3a-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="8fc3a-124">Bekijk in het detailvenster de lijst met afzonderlijke gebeurtenissen om uw gebeurtenis te zoeken.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="8fc3a-125">Klik op de gebeurtenis om specifieke details over een gebeurtenis te zien in het onderste deelvenster, onder de **tabbladen** Algemeen **en** Details.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="8fc3a-126">Gebeurtenis-id: 1000</span><span class="sxs-lookup"><span data-stu-id="8fc3a-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-127">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="8fc3a-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-129">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-129">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-130">
<b>Er is een antimalwarescan gestart. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="8fc3a-131">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-132">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-133">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-134">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-135">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-136">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-137">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-137">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-138">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-138">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-139">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-139">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-140">
</dt>
<dt>Scanbronnen: &lt; Resources (zoals bestanden/mappen/BHO) die zijn &gt; gescand.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-141">Gebeurtenis-id: 1001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-142">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-144">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-144">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-145">
<b>Een antimalwarescan is voltooid.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-146">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-147">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-148">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-149">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-150">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-151">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-152">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-152">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-153">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-153">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-154">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-154">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-155">
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Scantijd</dt>
<dt>van gebruiker: de duur van een &lt; scan. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-156">Gebeurtenis-id: 1002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-157">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-159">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-159">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-160">
<b>Een antimalwarescan is gestopt voordat deze is voltooid. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-161">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-162">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-163">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-164">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-165">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-166">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-167">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-167">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-168">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-168">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-169">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-169">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-170">
</dt>
<dt>Gebruiker: &lt; Domein &gt; &amp; lt; &gt;Scantijd</dt>
<dt>van gebruiker: de duur van een &lt; scan. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-171">Gebeurtenis-id: 1003</span><span class="sxs-lookup"><span data-stu-id="8fc3a-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-172">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-174">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-174">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-175">
<b>Een antimalwarescan is onderbroken. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-176">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-177">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-178">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-179">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-180">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-181">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-182">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-182">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-183">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-183">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-184">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-184">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-185">
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-186">Gebeurtenis-id: 1004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-187">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-189">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-189">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-190">
<b>Er is een antimalwarescan hervat. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-191">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-192">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-193">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-194">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-195">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-196">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-197">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-197">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-198">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-198">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-199">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-199">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-200">
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-201">Gebeurtenis-id: 1005</span><span class="sxs-lookup"><span data-stu-id="8fc3a-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-202">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-204">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-204">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-205">
<b>Een antimalwarescan is mislukt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-206">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="8fc3a-207">
<dt>Scan-id: &lt; Id-nummer van de &gt; relevante scan.</dt> 
<dt> Scantype: &lt; &gt; Scantype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-208">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-209">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-210">Antimalware</span></span></li>
</ul><span data-ttu-id="8fc3a-211">
</dt>
<dt>&lt;Scanparameters: &gt; Scanparameters, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-212">Volledige scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-212">Full scan</span></span></li>
<li><span data-ttu-id="8fc3a-213">Snelle scan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-213">Quick scan</span></span></li>
<li><span data-ttu-id="8fc3a-214">Klantscan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-214">Customer scan</span></span></li>
</ul><span data-ttu-id="8fc3a-215">
</dt>
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-216">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-217">Er is een fout opgetreden bij de antivirusclient en de huidige scan is gestopt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="8fc3a-218">De scan kan mislukken vanwege een probleem aan de clientzijde.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="8fc3a-219">Deze gebeurtenisrecord bevat de scan-id, het type scan (Microsoft Defender Antivirus, antispyware, antimalware), scanparameters, de gebruiker die de scan heeft gestart, de foutcode en een beschrijving van de fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="8fc3a-220">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8fc3a-221">Voer de scan opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="8fc3a-222">Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8fc3a-223">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-224">Gebeurtenis-id: 1006</span><span class="sxs-lookup"><span data-stu-id="8fc3a-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-225">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-227">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-227">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-228">
<b>De antimalware-engine heeft malware of andere mogelijk ongewenste software gevonden. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-229">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-230">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-231">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-232">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-232">Low</span></span></li>
<li><span data-ttu-id="8fc3a-233">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-233">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-234">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-234">High</span></span></li>
<li><span data-ttu-id="8fc3a-235">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-235">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-236">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-237">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-238">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-238">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-239">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-239">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-240">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-240">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-241">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-242">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-243">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-244">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-245">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-245">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-246">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-246">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-247">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-248">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-249">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-249">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-250">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-250">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-251">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-253">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-254">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-255">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-256">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-257">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-258">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-259">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-260"></dt>
<dt>UAC-status: &lt; &gt; Statusgebruiker:</dt>
<dt>Domein &lt; &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; pid-handtekeningversie:</dt>
<dt> &lt; engineversie van &gt; </dt>
<dt>definitieversie: Antimalware Engine &lt; versie &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-261">Gebeurtenis-id: 1007</span><span class="sxs-lookup"><span data-stu-id="8fc3a-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-262">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-264">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-264">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-265">
<b>Het antimalwareplatform heeft een actie uitgevoerd om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-266">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-267">Microsoft Defender Antivirus heeft actie ondernomen om deze computer te beschermen tegen malware of andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="8fc3a-268">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-269">
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt> &lt; &gt; Bedreigingsnaam-id:</dt>
<dt>Ernst van &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-270">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-270">Low</span></span></li>
<li><span data-ttu-id="8fc3a-271">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-271">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-272">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-272">High</span></span></li>
<li><span data-ttu-id="8fc3a-273">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-273">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-274">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt> Actie: &lt; Actie &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-275">Schoon: De resource is opgeschoond</span><span class="sxs-lookup"><span data-stu-id="8fc3a-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8fc3a-276">Quarantaine: De resource is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="8fc3a-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8fc3a-277">Verwijderen: De resource is verwijderd</span><span class="sxs-lookup"><span data-stu-id="8fc3a-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8fc3a-278">Toestaan: De resource is toegestaan om uit te voeren/te bestaan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8fc3a-279">Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8fc3a-280">Geen actie: geen actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-280">No action: No action</span></span></li>
<li><span data-ttu-id="8fc3a-281">Blokkering: De resource is geblokkeerd voor het uitvoeren van</span><span class="sxs-lookup"><span data-stu-id="8fc3a-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8fc3a-282">
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statushandtekeningsversie: &lt; engineversie &gt; van</dt>
<dt>definitieversie: &lt; Antimalware Engine versie &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-283">Gebeurtenis-id: 1008</span><span class="sxs-lookup"><span data-stu-id="8fc3a-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-284">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-286">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-286">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-287">
<b>Het antimalwareplatform heeft geprobeerd een actie uit te voeren om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software, maar de actie is mislukt.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-288">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-289">Microsoft Defender Antivirus is een fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="8fc3a-290">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-291">
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt> &lt; &gt; Bedreigingsnaam-id:</dt>
<dt>Ernst van &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-292">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-292">Low</span></span></li>
<li><span data-ttu-id="8fc3a-293">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-293">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-294">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-294">High</span></span></li>
<li><span data-ttu-id="8fc3a-295">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-295">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-296">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; &gt;Bestandspad</dt> 
<dt> actie: &lt; &gt; actie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-297">Schoon: De resource is opgeschoond</span><span class="sxs-lookup"><span data-stu-id="8fc3a-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8fc3a-298">Quarantaine: De resource is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="8fc3a-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8fc3a-299">Verwijderen: De resource is verwijderd</span><span class="sxs-lookup"><span data-stu-id="8fc3a-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8fc3a-300">Toestaan: De resource is toegestaan om uit te voeren/te bestaan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8fc3a-301">Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8fc3a-302">Geen actie: geen actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-302">No action: No action</span></span></li>
<li><span data-ttu-id="8fc3a-303">Blokkering: De resource is geblokkeerd voor het uitvoeren van</span><span class="sxs-lookup"><span data-stu-id="8fc3a-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8fc3a-304">
</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statushandtekeningsversie: &lt; engineversie &gt; van</dt>
<dt>definitieversie: &lt; Antimalware Engine versie &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-305">Gebeurtenis-id: 1009</span><span class="sxs-lookup"><span data-stu-id="8fc3a-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-306">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-308">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-308">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-309">
<b>Het antimalwareplatform heeft een item uit quarantaine hersteld. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-310">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-311">Microsoft Defender Antivirus heeft een item uit quarantaine hersteld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="8fc3a-312">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-313">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-314">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-314">Low</span></span></li>
<li><span data-ttu-id="8fc3a-315">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-315">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-316">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-316">High</span></span></li>
<li><span data-ttu-id="8fc3a-317">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-317">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-318">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-319">Gebeurtenis-id: 1010</span><span class="sxs-lookup"><span data-stu-id="8fc3a-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-320">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-322">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-322">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-323">
<b>Het antimalwareplatform kan een item niet herstellen uit quarantaine. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-324">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-325">Microsoft Defender Antivirus is een fout opgetreden bij het herstellen van een item uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="8fc3a-326">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-327">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-328">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-328">Low</span></span></li>
<li><span data-ttu-id="8fc3a-329">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-329">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-330">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-330">High</span></span></li>
<li><span data-ttu-id="8fc3a-331">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-331">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-332">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-333">Gebeurtenis-id: 1011</span><span class="sxs-lookup"><span data-stu-id="8fc3a-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-334">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-336">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-336">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-337">
<b>Het antimalwareplatform heeft een item uit quarantaine verwijderd. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-338">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-339">Microsoft Defender Antivirus heeft een item uit quarantaine verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="8fc3a-340">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-341">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-342">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-342">Low</span></span></li>
<li><span data-ttu-id="8fc3a-343">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-343">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-344">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-344">High</span></span></li>
<li><span data-ttu-id="8fc3a-345">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-345">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-346">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-347">Gebeurtenis-id: 1012</span><span class="sxs-lookup"><span data-stu-id="8fc3a-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-348">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-350">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-350">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-351">
<b>Het antimalwareplatform kan een item niet uit quarantaine verwijderen.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-352">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-353">Microsoft Defender Antivirus is een fout opgetreden bij het verwijderen van een item uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="8fc3a-354">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-355">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-356">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-356">Low</span></span></li>
<li><span data-ttu-id="8fc3a-357">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-357">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-358">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-358">High</span></span></li>
<li><span data-ttu-id="8fc3a-359">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-359">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-360">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; Gebruiker &gt; van</dt>
<dt> &lt; bestandspad: Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-361">Gebeurtenis-id: 1013</span><span class="sxs-lookup"><span data-stu-id="8fc3a-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-362">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-364">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-364">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-365">
<b>Het antimalwareplatform heeft de geschiedenis van malware en andere mogelijk ongewenste software verwijderd.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-366">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-367">Microsoft Defender Antivirus heeft de geschiedenis van malware en andere mogelijk ongewenste software verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8fc3a-368">
<dt>Tijd: de tijd waarop de gebeurtenis heeft plaatsgevonden, bijvoorbeeld wanneer de geschiedenis wordt verwijderd. Deze parameter wordt niet gebruikt bij bedreigingsgebeurtenissen, zodat er geen verwarring bestaat over de vraag of het hersteltijd of de tijd van de infectie is. Voor deze personen noemen we ze specifiek Actietijd of Detectietijd.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-369">Gebeurtenis-id: 1014</span><span class="sxs-lookup"><span data-stu-id="8fc3a-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-370">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-372">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-373">Het antimalwareplatform kan de geschiedenis van malware en andere mogelijk ongewenste software niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-374">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-375">Microsoft Defender Antivirus is een fout opgetreden bij het verwijderen van de geschiedenis van malware en andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8fc3a-376">
<dt>Tijd: de tijd waarop de gebeurtenis heeft plaatsgevonden, bijvoorbeeld wanneer de geschiedenis wordt verwijderd. Deze parameter wordt niet gebruikt bij bedreigingsgebeurtenissen, zodat er geen verwarring bestaat over de vraag of het hersteltijd of de tijd van de infectie is. Voor deze personen noemen we ze specifiek Actietijd of Detectietijd.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden. </dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-377">Gebeurtenis-id: 1015</span><span class="sxs-lookup"><span data-stu-id="8fc3a-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-378">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-380">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-380">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-381">
<b>Het antimalwareplatform heeft verdacht gedrag gedetecteerd.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-382">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-383">Microsoft Defender Antivirus heeft een verdacht gedrag gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="8fc3a-384">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-385">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-386">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-386">Low</span></span></li>
<li><span data-ttu-id="8fc3a-387">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-387">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-388">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-388">High</span></span></li>
<li><span data-ttu-id="8fc3a-389">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-389">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-390">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-391">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-392">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-392">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-393">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-393">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-394">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-394">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-395">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-396">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-397">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-398">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-399">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-399">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-400">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-400">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-401">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-402">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-403">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-403">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-404">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-404">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-405">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-407">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-408">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-409">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-410">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-411">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-412">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-413">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-414"></dt>
<dt>UAC-status: &lt; &gt; Statusgebruiker:</dt>
<dt>Domein &lt; &gt; \& lt; Naam &gt; </dt>
<dt>van gebruikersproces: &lt; proces &gt; in de PID-handtekening-id:</dt>de ernst van de gegevens die
<dt>overeenkomen met de ernst van de gegevens.</dt> 
<dt>Handtekeningversie: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: File name of the &lt; &gt; file.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-415">Gebeurtenis-id: 1116</span><span class="sxs-lookup"><span data-stu-id="8fc3a-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-416">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-418">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-418">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-419">
<b>Het antimalwareplatform heeft malware of andere mogelijk ongewenste software gedetecteerd. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-420">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-421">Microsoft Defender Antivirus heeft malware of andere mogelijk ongewenste software gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8fc3a-422">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-423">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-424">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-424">Low</span></span></li>
<li><span data-ttu-id="8fc3a-425">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-425">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-426">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-426">High</span></span></li>
<li><span data-ttu-id="8fc3a-427">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-427">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-428">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-429">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-430">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-430">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-431">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-431">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-432">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-432">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-433">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-434">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-435">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-436">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-437">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-437">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-438">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-438">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-439">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-440">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-441">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-441">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-442">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-442">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-443">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-445">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-446">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-447">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-448">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-449">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-450">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-451">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-452"></dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; pid-handtekeningversie:</dt>
<dt> &lt; &gt; Engine-versie</dt>van
<dt>definitieversie: Versie &lt; antimalware-engine &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-453">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-454">Er is geen actie vereist.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-454">No action is required.</span></span> <span data-ttu-id="8fc3a-455">Microsoft Defender Antivirus kan deze bedreiging opschorten en routinematige actie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="8fc3a-456">Als u de bedreiging handmatig wilt verwijderen, klikt u in de Microsoft Defender Antivirus-interface op <b>Computer reinigen.</b></span><span class="sxs-lookup"><span data-stu-id="8fc3a-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-457">Gebeurtenis-id: 1117</span><span class="sxs-lookup"><span data-stu-id="8fc3a-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-458">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-460">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-460">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-461">
<b>Het antimalwareplatform heeft een actie uitgevoerd om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-462">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-463">Microsoft Defender Antivirus heeft actie ondernomen om deze computer te beschermen tegen malware of andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8fc3a-464">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-465">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-466">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-466">Low</span></span></li>
<li><span data-ttu-id="8fc3a-467">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-467">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-468">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-468">High</span></span></li>
<li><span data-ttu-id="8fc3a-469">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-469">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-470">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-471">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-472">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-472">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-473">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-473">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-474">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-474">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-475">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-476">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-477">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-478">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-479">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-479">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-480">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-480">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-481">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-482">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-483">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-483">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-484">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-484">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-485">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-487">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-488">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-489">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-490">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-491">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-492">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-493">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-494"></dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-495">Schoon: De resource is opgeschoond</span><span class="sxs-lookup"><span data-stu-id="8fc3a-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8fc3a-496">Quarantaine: De resource is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="8fc3a-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8fc3a-497">Verwijderen: De resource is verwijderd</span><span class="sxs-lookup"><span data-stu-id="8fc3a-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8fc3a-498">Toestaan: De resource is toegestaan om uit te voeren/te bestaan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8fc3a-499">Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8fc3a-500">Geen actie: geen actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-500">No action: No action</span></span></li>
<li><span data-ttu-id="8fc3a-501">Blokkering: De resource is geblokkeerd voor het uitvoeren van</span><span class="sxs-lookup"><span data-stu-id="8fc3a-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8fc3a-502">
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine Version: &lt; Antimalware Engine &gt; version</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="8fc3a-503">Standaardinstelling voor Internet Explorer of Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8fc3a-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="8fc3a-504">Instellingen voor Gebruikerstoegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="8fc3a-505">Chrome-instellingen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-505">Chrome settings</span></span></li>
<li><span data-ttu-id="8fc3a-506">Opstartbeheergegevens</span><span class="sxs-lookup"><span data-stu-id="8fc3a-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="8fc3a-507">Registerinstellingen voor Regedit en Task Manager</span><span class="sxs-lookup"><span data-stu-id="8fc3a-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="8fc3a-508">Windows Update, Background Intelligent Transfer Service en Remote Procedure Call Service</span><span class="sxs-lookup"><span data-stu-id="8fc3a-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="8fc3a-509">Windows Besturingssysteembestanden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="8fc3a-510">De bovenstaande context is van toepassing op de volgende client- en serverversies:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="8fc3a-511">Besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-511">Operating system</span></span></th>
<th><span data-ttu-id="8fc3a-512">Versie van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-513">Clientbesturingssysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="8fc3a-514">Windows Vista (Service Pack 1 of Service Pack 2), Windows 7 en hoger</span><span class="sxs-lookup"><span data-stu-id="8fc3a-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-515">Serverbesturingssysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="8fc3a-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 en Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8fc3a-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-517">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-518">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-518">No action is necessary.</span></span> <span data-ttu-id="8fc3a-519">Microsoft Defender Antivirus een bedreiging verwijderd of in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-520">Gebeurtenis-id: 1118</span><span class="sxs-lookup"><span data-stu-id="8fc3a-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-521">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-523">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-523">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-524">
<b>Het antimalwareplatform heeft geprobeerd een actie uit te voeren om uw systeem te beschermen tegen malware of andere mogelijk ongewenste software, maar de actie is mislukt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-525">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-526">Microsoft Defender Antivirus is een niet-kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8fc3a-527">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-528">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-529">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-529">Low</span></span></li>
<li><span data-ttu-id="8fc3a-530">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-530">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-531">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-531">High</span></span></li>
<li><span data-ttu-id="8fc3a-532">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-532">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-533">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-534">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-535">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-535">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-536">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-536">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-537">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-537">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-538">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-539">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-540">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-541">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-542">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-542">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-543">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-543">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-544">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-545">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-546">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-546">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-547">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-547">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-548">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-550">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-551">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-552">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-553">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-554">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-555">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-556">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-557"></dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-558">Schoon: De resource is opgeschoond</span><span class="sxs-lookup"><span data-stu-id="8fc3a-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8fc3a-559">Quarantaine: De resource is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="8fc3a-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8fc3a-560">Verwijderen: De resource is verwijderd</span><span class="sxs-lookup"><span data-stu-id="8fc3a-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8fc3a-561">Toestaan: De resource is toegestaan om uit te voeren/te bestaan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8fc3a-562">Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8fc3a-563">Geen actie: geen actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-563">No action: No action</span></span></li>
<li><span data-ttu-id="8fc3a-564">Blokkering: De resource is geblokkeerd voor het uitvoeren van</span><span class="sxs-lookup"><span data-stu-id="8fc3a-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8fc3a-565">
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-566">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-567">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-567">No action is necessary.</span></span> <span data-ttu-id="8fc3a-568">Microsoft Defender Antivirus taak met betrekking tot de herstel van malware is niet voltooid.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="8fc3a-569">Dit is geen kritieke fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-570">Gebeurtenis-id: 1119</span><span class="sxs-lookup"><span data-stu-id="8fc3a-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-571">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-573">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-573">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-574">
<b>Op het antimalwareplatform is een kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software. Er zijn meer details in het gebeurtenisbericht.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-575">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-576">Microsoft Defender Antivirus is een kritieke fout opgetreden bij het ondernemen van actie tegen malware of andere mogelijk ongewenste software.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="8fc3a-577">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="8fc3a-578">
<dt>Naam: &lt; Bedreigingsnaam-id: &gt; </dt>Ernst van
<dt> &lt; &gt; bedreigings-id:</dt> 
<dt> &lt; &gt; ernst, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-579">Laag</span><span class="sxs-lookup"><span data-stu-id="8fc3a-579">Low</span></span></li>
<li><span data-ttu-id="8fc3a-580">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8fc3a-580">Moderate</span></span></li>
<li><span data-ttu-id="8fc3a-581">Hoog</span><span class="sxs-lookup"><span data-stu-id="8fc3a-581">High</span></span></li>
<li><span data-ttu-id="8fc3a-582">Ernstig</span><span class="sxs-lookup"><span data-stu-id="8fc3a-582">Severe</span></span></li>
</ul><span data-ttu-id="8fc3a-583">
</dt>
<dt>Categorie: &lt; &gt;Categoriebeschrijving, bijvoorbeeld een bedreiging of malwaretype.</dt> 
<dt>Pad: &lt; File &gt; path</dt> 
<dt> Detection Origin: &lt; Detection origin &gt; , bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="8fc3a-584">Unknown</span></span></li>
<li><span data-ttu-id="8fc3a-585">Lokale computer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-585">Local computer</span></span></li>
<li><span data-ttu-id="8fc3a-586">Netwerk delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-586">Network share</span></span></li>
<li><span data-ttu-id="8fc3a-587">Internet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-587">Internet</span></span></li>
<li><span data-ttu-id="8fc3a-588">Binnenkomend verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="8fc3a-589">Uitgaand verkeer</span><span class="sxs-lookup"><span data-stu-id="8fc3a-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="8fc3a-590">
</dt>
<dt>Detectietype: &lt; &gt; detectietype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="8fc3a-591">Heuristics</span></span></li>
<li><span data-ttu-id="8fc3a-592">Generic</span><span class="sxs-lookup"><span data-stu-id="8fc3a-592">Generic</span></span></li>
<li><span data-ttu-id="8fc3a-593">Beton</span><span class="sxs-lookup"><span data-stu-id="8fc3a-593">Concrete</span></span></li>
<li><span data-ttu-id="8fc3a-594">Dynamische handtekening</span><span class="sxs-lookup"><span data-stu-id="8fc3a-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="8fc3a-595">
</dt>
<dt>Detectiebron: &lt; &gt; detectiebron bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-596">Gebruiker: gebruiker gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-596">User: user initiated</span></span></li>
<li><span data-ttu-id="8fc3a-597">Systeem: systeem gestart</span><span class="sxs-lookup"><span data-stu-id="8fc3a-597">System: system initiated</span></span></li>
<li><span data-ttu-id="8fc3a-598">Realtime: in realtime gestarte component</span><span class="sxs-lookup"><span data-stu-id="8fc3a-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="8fc3a-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span><span class="sxs-lookup"><span data-stu-id="8fc3a-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="8fc3a-600">NIS: Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="8fc3a-601">IEPROTECT: IE - IExtensionValidation; dit beschermt tegen schadelijke besturingselementen voor webpagina's</span><span class="sxs-lookup"><span data-stu-id="8fc3a-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="8fc3a-602">Early Launch Antimalware (ELAM).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="8fc3a-603">Dit geldt ook voor malware die is gedetecteerd door de opstartvolgorde</span><span class="sxs-lookup"><span data-stu-id="8fc3a-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="8fc3a-604">Externe bevestiging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="8fc3a-605">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="8fc3a-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="8fc3a-606">Wordt voornamelijk gebruikt om scripts (PS, VBS) te beveiligen, maar kan ook door derden worden aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="8fc3a-607"></dt>
<dt>UAC-gebruiker: &lt; Domein &gt; \& lt; &gt;Gebruikersnaam:</dt>
<dt>Proces in de &lt; &gt; PID-actie:</dt> 
<dt> &lt; &gt; Actie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="8fc3a-608">Schoon: De resource is opgeschoond</span><span class="sxs-lookup"><span data-stu-id="8fc3a-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="8fc3a-609">Quarantaine: De resource is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="8fc3a-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="8fc3a-610">Verwijderen: De resource is verwijderd</span><span class="sxs-lookup"><span data-stu-id="8fc3a-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="8fc3a-611">Toestaan: De resource is toegestaan om uit te voeren/te bestaan</span><span class="sxs-lookup"><span data-stu-id="8fc3a-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="8fc3a-612">Gebruiker gedefinieerd: door de gebruiker gedefinieerde actie die normaal gesproken afkomstig is van deze lijst met acties die de gebruiker heeft opgegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="8fc3a-613">Geen actie: geen actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-613">No action: No action</span></span></li>
<li><span data-ttu-id="8fc3a-614">Blokkering: De resource is geblokkeerd voor het uitvoeren van</span><span class="sxs-lookup"><span data-stu-id="8fc3a-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="8fc3a-615">
</dt>
<dt>Actiestatus: &lt; Beschrijving van &gt; aanvullende acties</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine-versie: &lt; Antimalware Engine &gt; versie</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-616">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-617">De Microsoft Defender Antivirus client heeft deze fout ondervonden vanwege kritieke problemen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="8fc3a-618">Het eindpunt is mogelijk niet beveiligd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-618">The endpoint might not be protected.</span></span> <span data-ttu-id="8fc3a-619">Bekijk de foutbeschrijving en volg de onderstaande <b>actiestappen</b> voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="8fc3a-620">Actie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-620">Action</span></span></th>
<th><span data-ttu-id="8fc3a-621">Actie voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="8fc3a-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-622">
<b>Verwijderen</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-623">Werk de definities bij en controleer of de verwijdering is gelukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-624">
<b>Opruimen</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-625">Werk de definities bij en controleer of de herstelslag is gelukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-626">
<b>Quarantaine</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-627">Werk de definities bij en controleer of de gebruiker toestemming heeft om toegang te krijgen tot de benodigde resources.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-628">
<b>Toestaan</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-629">Controleer of de gebruiker toestemming heeft om toegang te krijgen tot de benodigde resources.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="8fc3a-630">Als deze gebeurtenis blijft bestaan:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="8fc3a-631">Voer de scan opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="8fc3a-632">Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8fc3a-633">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-634">Gebeurtenis-id: 1120</span><span class="sxs-lookup"><span data-stu-id="8fc3a-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-635">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-637">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-637">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-638">
<b>Microsoft Defender Antivirus heeft de hashes voor een bedreigingsbron afgeleid.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-639">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-640">Microsoft Defender Antivirus client is in een gezonde staat actief.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="8fc3a-641">
<dt>Huidige platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="8fc3a-642"><b>Opmerking: Deze gebeurtenis wordt alleen geregistreerd als het volgende beleid is ingesteld: <b>ThreatFileHashLogging unsigned</b>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-643">Gebeurtenis-id: 1150</span><span class="sxs-lookup"><span data-stu-id="8fc3a-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-644">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-646">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-646">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-647">
<b>Als uw antimalwareplatform de status rapporteert aan een monitoringplatform, geeft deze gebeurtenis aan dat het antimalwareplatform actief is en in een goede staat is. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-648">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-649">Microsoft Defender Antivirus client is in een gezonde staat actief.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="8fc3a-650">
<dt>Platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Signature Version: Definition &lt; version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-651">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-652">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-652">No action is necessary.</span></span> <span data-ttu-id="8fc3a-653">De Microsoft Defender Antivirus client is in een gezonde staat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8fc3a-654">Deze gebeurtenis wordt op uurbasis gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="8fc3a-655">Gebeurtenis-id: 1151</span><span class="sxs-lookup"><span data-stu-id="8fc3a-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-656">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-658">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-658">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-659">
<b>Endpoint Protection client health report (time in UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-660">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-661">Rapport over de status van de antivirusclient.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="8fc3a-662">
<dt>Platformversie: &lt; Huidige platformversie &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine &gt; </dt>version
<dt>Network Realtime Inspection engine &lt; &gt; version: Network Realtime Inspection</dt>engine Antivirus signature
<dt>version: Antivirus &lt; signature &gt; </dt>version
<dt>Antispyware signature version: &lt; &gt; </dt>
<dt> &lt; &gt; </dt>Antispyware signature version Network Realtime Inspection signature version: Network Realtime Inspection signature version
<dt>RTP state: &lt; Realtime protection state &gt; (Enabled or Disabled)</dt>
<dt>OA state: On Access state &lt; &gt; (Enabled</dt>or Disabled)
<dt>IOAV state: IE Downloads and IE Downloads and &lt; Outlook Express Attachments state &gt; (Enabled</dt>or Disabled) BM
<dt>state: Behavior Monitoring state &lt; &gt; (Enabled or Disabled)</dt>Antivirus signature
<dt>age: Antivirus signature age &lt; &gt; (in days)</dt>
<dt>Antispyware signature age: Antispyware signature age &lt; &gt; (in days)</dt>Last quick scan age(in days) Last quick scan age
<dt> &lt; &gt; (in days)</dt>Last full scan age: Last full scan age
<dt> &lt; &gt; (in days)</dt>Antivirus signature creation
<dt>time: ? &lt; Tijd voor &gt; het maken van</dt>
<dt>antivirushandtekeningen Antispyware-handtekening: ? &lt; Antispyware signature &gt; creation time Last</dt>
<dt>quick scan start time: ? &lt; Laatste begintijd &gt; snelle scan Laatste</dt>
<dt>eindtijd snelle scan: ? &lt; &gt;</dt>Laatste eindtijd snelle scan Laatste snelle scanbron: Laatste snelle scanbron
<dt> &lt; (0 = scan&#39;niet &gt; uitgevoerd, 1 = gebruiker gestart, 2 =</dt>systeem gestart) Laatste volledige begintijd van de
<dt>scan: ? &lt; Laatste volledige begintijd &gt; van de scan</dt>Laatste volledige
<dt>eindtijd van de scan: ? &lt; &gt;</dt>Laatste volledige eindtijd van de scan Laatste volledige scanbron: Laatste volledige
<dt> &lt; scanbron &gt; (0 = scan&#39;niet uitgevoerd, 1 = gebruiker gestart, 2 =</dt>systeem gestart) Productstatus: Voor interne probleemoplossing 
<dt></span><span class="sxs-lookup"><span data-stu-id="8fc3a-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="8fc3a-663">
<th colspan="2">Gebeurtenis-id: 2000</span><span class="sxs-lookup"><span data-stu-id="8fc3a-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-664">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-666">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-666">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-667">
<b>De antimalwaredefinities zijn bijgewerkt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-668">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-669">Antivirushandtekeningsversie is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="8fc3a-670">
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Vorige handtekeningversie: Handtekeningtype &lt; &gt; </dt>vorige handtekeningversie: type 
<dt> &lt; &gt; handtekening, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8fc3a-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-671">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-672">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-673">Antimalware</span></span></li>
<li><span data-ttu-id="8fc3a-674">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-675">
</dt>
<dt>Type update: &lt; Updatetype &gt; , volledig of Delta.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-676">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-677">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-677">No action is necessary.</span></span> <span data-ttu-id="8fc3a-678">De Microsoft Defender Antivirus client is in een gezonde staat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8fc3a-679">Deze gebeurtenis wordt gerapporteerd wanneer handtekeningen zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-680">Gebeurtenis-id: 2001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-681">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-683">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-683">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-684">
<b>De beveiligingsintelligentieupdate is mislukt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-685">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-686">Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van handtekeningen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="8fc3a-687">
<dt>Nieuwe versie van beveiligingsinformatie: &lt; Nieuw versienummer &gt; </dt>
<dt>Vorige versie van beveiligingsinformatie: Vorige &lt; versie &gt; </dt> 
<dt> Updatebron: &lt; &gt; Updatebron, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-688">Updatemap voor beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="8fc3a-689">Interne beveiligingsinformatieupdateserver</span><span class="sxs-lookup"><span data-stu-id="8fc3a-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="8fc3a-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="8fc3a-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="8fc3a-691">Bestands delen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-691">File share</span></span></li>
<li><span data-ttu-id="8fc3a-692">Microsoft Centrum voor beveiliging tegen schadelijke software (MMPC)</span><span class="sxs-lookup"><span data-stu-id="8fc3a-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="8fc3a-693">
</dt>
<dt>Updatefase: &lt; &gt; Updatefase, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-694">Zoeken</span><span class="sxs-lookup"><span data-stu-id="8fc3a-694">Search</span></span></li>
<li><span data-ttu-id="8fc3a-695">Downloaden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-695">Download</span></span></li>
<li><span data-ttu-id="8fc3a-696">Installeren</span><span class="sxs-lookup"><span data-stu-id="8fc3a-696">Install</span></span></li>
</ul><span data-ttu-id="8fc3a-697">
</dt>
<dt>Bronpad: Bestandsaandeelnaam voor Unc (Universal Naming Convention), servernaam voor Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Type handtekening: &lt; type &gt; handtekening, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8fc3a-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-698">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-699">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-700">Antimalware</span></span></li>
<li><span data-ttu-id="8fc3a-701">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-702">
</dt>
<dt>Type update: &lt; Updatetype &gt; , volledig of Delta.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-703">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-704">Deze fout treedt op wanneer er een probleem is met het bijwerken van definities.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="8fc3a-705">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8fc3a-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Werk definities</a> bij en dwing een rescan rechtstreeks op het eindpunt af.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="8fc3a-707">Bekijk de vermeldingen in het bestand %Windir%\WindowsUpdate.log voor meer informatie over deze fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="8fc3a-708">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-709">Gebeurtenis-id: 2002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-710">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-712">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-712">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-713">
<b>De antimalware-engine is bijgewerkt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-714">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-715">Microsoft Defender Antivirus engine-versie is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="8fc3a-716">
<dt>Huidige engine-versie: &lt; Huidige engine &gt; versie</dt>
<dt>Vorige engine versie: Vorige engine &lt; versie &gt; </dt>Engine
<dt>Type: Engine type , ofwel &lt; &gt; antimalware engine of Network Inspection System engine.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; Gebruiker &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-717">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-718">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-718">No action is necessary.</span></span> <span data-ttu-id="8fc3a-719">De Microsoft Defender Antivirus client is in een gezonde staat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8fc3a-720">Deze gebeurtenis wordt gerapporteerd wanneer de antimalware-engine is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-721">Gebeurtenis-id: 2003</span><span class="sxs-lookup"><span data-stu-id="8fc3a-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-722">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-724">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-724">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-725">
<b>De update van de antimalware-engine is mislukt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-726">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-727">Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van de engine.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="8fc3a-728">
<dt>Nieuwe engineversie:</dt>
<dt>vorige engineversie: vorige &lt; &gt; motorversie</dt>
<dt>Motortype: &lt; Motortype , &gt; antimalware-engine of Network Inspection System-engine.</dt> 
<dt>Gebruiker: &lt; Domein &gt; \& lt; &gt;</dt>
<dt>Gebruikersfoutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-729">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-730">De Microsoft Defender Antivirus clientupdate is mislukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="8fc3a-731">Deze gebeurtenis treedt op wanneer de client zichzelf niet kan bijwerken.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="8fc3a-732">Deze gebeurtenis is meestal het gevolg van een onderbreking van de netwerkverbinding tijdens een update.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="8fc3a-733">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8fc3a-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Werk definities</a> bij en dwing een rescan rechtstreeks op het eindpunt af.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="8fc3a-735">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-736">Gebeurtenis-id: 2004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-737">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-739">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-739">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-740">
<b>Er is een probleem met het laden van antimalwaredefinities. De antimalware-engine probeert de laatst bekende goede set definities te laden.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-741">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-742">Microsoft Defender Antivirus is een fout opgetreden bij het laden van handtekeningen en wordt geprobeerd terug te keren naar een bekende set handtekeningen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="8fc3a-743">
<dt>Handtekeningen Geprobeerd:</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Handtekeningversie: &lt; Definitieversie &gt; </dt>
<dt>Engine Version: &lt; Antimalware engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-744">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-745">De Microsoft Defender Antivirus client heeft geprobeerd het meest recente definitiebestand te downloaden en te installeren en is mislukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="8fc3a-746">Deze fout kan optreden wanneer de client een fout ondervindt tijdens het laden van de definities of als het bestand beschadigd is.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="8fc3a-747">Microsoft Defender Antivirus probeert terug te keren naar een bekende verzameling definities.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="8fc3a-748">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8fc3a-749">Start de computer opnieuw en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="8fc3a-750">Download de meest recente definities van <a href="https://aka.ms/wdsi">de Microsoft-beveiligingsinformatie site.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="8fc3a-751">Opmerking: De grootte van het definitiebestand dat van de site is gedownload, kan groter zijn dan 60 MB en mag niet worden gebruikt als een langetermijnoplossing voor het bijwerken van definities.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="8fc3a-752">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-753">Gebeurtenis-id: 2005</span><span class="sxs-lookup"><span data-stu-id="8fc3a-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-754">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-756">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-756">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-757">
<b>De antimalware-engine kan niet worden geladen omdat het antimalwareplatform verouderd is. Het antimalware-platform laadt de laatst bekende goede antimalware-engine en probeert bij te werken.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-758">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-759">Microsoft Defender Antivirus kan geen antimalware-engine laden omdat de huidige platformversie niet wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="8fc3a-760">Microsoft Defender Antivirus terug naar de laatste bekende goede engine en wordt een platformupdate geprobeerd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="8fc3a-761">
<dt>Huidige platformversie: &lt; huidige platformversie&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-762">Gebeurtenis-id: 2006</span><span class="sxs-lookup"><span data-stu-id="8fc3a-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-763">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-765">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-765">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-766">
<b>De platformupdate is mislukt. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-767">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-768">Microsoft Defender Antivirus is een fout opgetreden bij het bijwerken van het platform.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="8fc3a-769">
<dt>Huidige platformversie: &lt; Huidige platformversie &gt; </dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-770">Gebeurtenis-id: 2007</span><span class="sxs-lookup"><span data-stu-id="8fc3a-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-771">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-773">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-773">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-774">
<b>Het platform is binnenkort verouderd. Download het nieuwste platform om de nieuwste beveiliging te behouden.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-775">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-776">Microsoft Defender Antivirus binnenkort een nieuwere platformversie nodig om toekomstige versies van de antimalware-engine te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="8fc3a-777">Download het nieuwste Microsoft Defender Antivirus platform om het beste beschermingsniveau te behouden dat beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="8fc3a-778">
<dt>Huidige platformversie: &lt; huidige platformversie&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-779">Gebeurtenis-id: 2010</span><span class="sxs-lookup"><span data-stu-id="8fc3a-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-780">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-782">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-782">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-783">
<b>De antimalware-engine heeft de Dynamic Signature Service gebruikt om aanvullende definities te krijgen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-784">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-785">Microsoft Defender Antivirus <i>Dynamic Signature Service gebruikt om</i> extra handtekeningen op te halen om uw computer te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="8fc3a-786">
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8fc3a-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-787">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-788">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-789">Antimalware</span></span></li>
<li><span data-ttu-id="8fc3a-790">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-791">
</dt>
<dt>Huidige engine-versie: &lt; Huidige engineversie &gt; </dt> 
<dt> Dynamic Signature Type: Dynamisch &lt; &gt; handtekeningtype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-792">Versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-792">Version</span></span></li>
<li><span data-ttu-id="8fc3a-793">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-793">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-794">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-794">No limit</span></span></li>
<li><span data-ttu-id="8fc3a-795">Duur</span><span class="sxs-lookup"><span data-stu-id="8fc3a-795">Duration</span></span></li>
</ul><span data-ttu-id="8fc3a-796">
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistent limit type , &gt; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-797">VDM-versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-797">VDM version</span></span></li>
<li><span data-ttu-id="8fc3a-798">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-798">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-799">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-799">No limit</span></span></li>
</ul><span data-ttu-id="8fc3a-800">
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-801">Gebeurtenis-id: 2011</span><span class="sxs-lookup"><span data-stu-id="8fc3a-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-802">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-804">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-804">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-805">
<b>De Dynamische handtekeningservice heeft de verouderd dynamische definities verwijderd. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-806">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-807">Microsoft Defender Antivirus <i>Dynamic Signature Service gebruikt om</i> verouderde handtekeningen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="8fc3a-808">
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8fc3a-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-809">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-810">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-811">Antimalware</span></span></li>
<li><span data-ttu-id="8fc3a-812">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-813">
</dt>
<dt>Huidige engine-versie: &lt; Huidige engineversie &gt; </dt> 
<dt> Dynamic Signature Type: Dynamisch &lt; &gt; handtekeningtype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-814">Versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-814">Version</span></span></li>
<li><span data-ttu-id="8fc3a-815">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-815">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-816">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-816">No limit</span></span></li>
<li><span data-ttu-id="8fc3a-817">Duur</span><span class="sxs-lookup"><span data-stu-id="8fc3a-817">Duration</span></span></li>
</ul><span data-ttu-id="8fc3a-818">
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistent Limit Type: Persistent limit type , &lt; &gt; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-819">VDM-versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-819">VDM version</span></span></li>
<li><span data-ttu-id="8fc3a-820">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-820">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-821">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-821">No limit</span></span></li>
</ul><span data-ttu-id="8fc3a-822">
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-823">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-824">Er is geen actie nodig.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-824">No action is necessary.</span></span> <span data-ttu-id="8fc3a-825">De Microsoft Defender Antivirus client is in een gezonde staat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="8fc3a-826">Deze gebeurtenis wordt gerapporteerd wanneer de dynamische handtekeningservice de actuele dynamische definities verwijdert.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-827">Gebeurtenis-id: 2012</span><span class="sxs-lookup"><span data-stu-id="8fc3a-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-828">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-830">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-830">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-831">
<b>De antimalware-engine heeft een foutmelding ondervonden bij het gebruik van de Dynamic Signature Service. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-832">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-833">Microsoft Defender Antivirus is een fout opgetreden bij het gebruik van <i>Dynamic Signature Service.</i></span><span class="sxs-lookup"><span data-stu-id="8fc3a-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="8fc3a-834">
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt> 
<dt> Handtekeningtype: &lt; type &gt; handtekening, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="8fc3a-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="8fc3a-835">Antivirus</span></span></li>
<li><span data-ttu-id="8fc3a-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-836">Antispyware</span></span></li>
<li><span data-ttu-id="8fc3a-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="8fc3a-837">Antimalware</span></span></li>
<li><span data-ttu-id="8fc3a-838">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-839">
</dt>
<dt>Huidige engine-versie: &lt; Huidige engine-versie &gt; </dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt> Type dynamische handtekening: &lt; dynamisch &gt; handtekeningtype, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-840">Versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-840">Version</span></span></li>
<li><span data-ttu-id="8fc3a-841">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-841">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-842">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-842">No limit</span></span></li>
<li><span data-ttu-id="8fc3a-843">Duur</span><span class="sxs-lookup"><span data-stu-id="8fc3a-843">Duration</span></span></li>
</ul><span data-ttu-id="8fc3a-844">
</dt>
<dt>Persistentiepad: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature
<dt>Compilatie Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistent limit type , &gt; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-845">VDM-versie</span><span class="sxs-lookup"><span data-stu-id="8fc3a-845">VDM version</span></span></li>
<li><span data-ttu-id="8fc3a-846">Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8fc3a-846">Timestamp</span></span></li>
<li><span data-ttu-id="8fc3a-847">Geen limiet</span><span class="sxs-lookup"><span data-stu-id="8fc3a-847">No limit</span></span></li>
</ul><span data-ttu-id="8fc3a-848">
</dt>
<dt>Persistentielimiet: persistentielimiet van de fastpath-handtekening.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-849">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-850">Controleer de instellingen voor uw internetverbinding.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-851">Gebeurtenis-id: 2013</span><span class="sxs-lookup"><span data-stu-id="8fc3a-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-852">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-854">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-854">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-855">
<b>De Dynamische handtekeningservice heeft alle dynamische definities verwijderd. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-856">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-857">Microsoft Defender Antivirus alle <i>dynamische handtekeningservicehandtekeningen</i> verwijderd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="8fc3a-858">
<dt>Huidige handtekeningversie: &lt; huidige handtekeningversie&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-859">Gebeurtenis-id: 2020</span><span class="sxs-lookup"><span data-stu-id="8fc3a-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-860">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-862">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-862">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-863">
<b>De antimalware-engine heeft een schoon bestand gedownload. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-864">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-865">Microsoft Defender Antivirus een schoon bestand gedownload.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="8fc3a-866">
<dt>Bestandsnaam: &lt; Bestandsnaam &gt; Van het bestand.</dt> 
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-867">Gebeurtenis-id: 2021</span><span class="sxs-lookup"><span data-stu-id="8fc3a-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-868">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-870">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-870">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-871">
<b>De antimalware-engine kan geen schoon bestand downloaden. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-872">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-873">Microsoft Defender Antivirus is een fout opgetreden bij het downloaden van een schoon bestand.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="8fc3a-874">
<dt>Bestandsnaam: &lt; Bestandsnaam &gt; Van het bestand.</dt> 
<dt>Huidige handtekeningversie: &lt; Huidige handtekeningversie &gt; </dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>Error
<dt>Code: Error code Result code associated with &lt; threat &gt; status. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-875">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-876">Controleer de instellingen voor uw internetverbinding.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="8fc3a-877">De Microsoft Defender Antivirus client heeft een fout ondervonden bij het gebruik van de Dynamic Signature Service om de meest recente definities naar een specifieke bedreiging te downloaden.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="8fc3a-878">Deze fout wordt waarschijnlijk veroorzaakt door een probleem met de netwerkverbinding.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-879">Gebeurtenis-id: 2030</span><span class="sxs-lookup"><span data-stu-id="8fc3a-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-880">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-882">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-882">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-883">
<b>De antimalware-engine is gedownload en is geconfigureerd om offline te worden uitgevoerd bij de volgende systeemstart.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-884">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-885">Microsoft Defender Antivirus offline antivirusprogramma gedownload en geconfigureerd om bij de volgende herstart uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-886">Gebeurtenis-id: 2031</span><span class="sxs-lookup"><span data-stu-id="8fc3a-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-887">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-889">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-889">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-890">
<b>De antimalware-engine kan een offlinescan niet downloaden en configureren.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-891">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-892">Microsoft Defender Antivirus is een fout opgetreden bij het downloaden en configureren van offline antivirusprogramma's.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="8fc3a-893">
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-894">Gebeurtenis-id: 2040</span><span class="sxs-lookup"><span data-stu-id="8fc3a-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-895">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-897">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-897">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-898">
<b>Antimalware-ondersteuning voor deze versie van het besturingssysteem eindigt binnenkort. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-899">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-900">De ondersteuning voor uw besturingssysteem verloopt binnenkort.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="8fc3a-901">Het Microsoft Defender Antivirus uitvoeren op een niet-ondersteunend besturingssysteem is geen geschikte oplossing om u te beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-902">Gebeurtenis-id: 2041</span><span class="sxs-lookup"><span data-stu-id="8fc3a-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-903">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-905">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-905">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-906">
<b>De ondersteuning voor antimalware voor dit besturingssysteem is beëindigd. U moet het besturingssysteem upgraden voor verdere ondersteuning. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-907">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-908">De ondersteuning voor uw besturingssysteem is verlopen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-908">The support for your operating system has expired.</span></span> <span data-ttu-id="8fc3a-909">Het Microsoft Defender Antivirus uitvoeren op een niet-ondersteunend besturingssysteem is geen geschikte oplossing om u te beschermen tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-910">Gebeurtenis-id: 2042</span><span class="sxs-lookup"><span data-stu-id="8fc3a-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-911">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-913">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-913">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-914">
<b>De antimalware-engine ondersteunt dit besturingssysteem niet meer en beschermt uw systeem niet meer tegen malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-915">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-916">De ondersteuning voor uw besturingssysteem is verlopen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-916">The support for your operating system has expired.</span></span> <span data-ttu-id="8fc3a-917">Microsoft Defender Antivirus wordt niet meer ondersteund op uw besturingssysteem, werkt niet meer en beschermt niet meer tegen malwaredreigingen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-918">Gebeurtenis-id: 3002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-919">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-921">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-921">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-922">
<b>Er is een fout opgetreden bij realtimebeveiliging en is mislukt.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-923">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-924">Microsoft Defender Antivirus Real-Time Protection-functie is een fout opgetreden en is mislukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="8fc3a-925">
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-926">Op Access</span><span class="sxs-lookup"><span data-stu-id="8fc3a-926">On Access</span></span></li>
<li><span data-ttu-id="8fc3a-927">Internet Explorer-downloads en Microsoft Outlook Express-bijlagen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8fc3a-928">Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="8fc3a-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8fc3a-929">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-930">
</dt>
<dt>Foutcode: &lt; Foutcode &gt; Resultaatcode die is gekoppeld aan de bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt> 
<dt>Reden: De reden Microsoft Defender Antivirus realtimebeveiliging een functie opnieuw heeft gestart.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-931">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-932">Start het systeem opnieuw op en voer een volledige scan uit omdat&#39;mogelijk dat het systeem enige tijd niet is beveiligd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="8fc3a-933">De Microsoft Defender Antivirus client&#39;in realtime beveiligingsfunctie is een fout opgetreden omdat een van de services niet kon worden begonnen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="8fc3a-934">Als dit wordt gevolgd door een gebeurtenis-id van 3007, is de fout tijdelijk en is de antimalwareclient hersteld van de fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-935">Gebeurtenis-id: 3007</span><span class="sxs-lookup"><span data-stu-id="8fc3a-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-936">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-938">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-938">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-939">
<b>Realtimebeveiliging hersteld van een fout. Het is raadzaam een volledige systeemscan uit te voeren wanneer u deze fout ziet. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-940">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-941">Microsoft Defender Antivirus Real-time Protection heeft een functie opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="8fc3a-942">U wordt aangeraden een volledige systeemscan uit te voeren om items te detecteren die mogelijk zijn gemist terwijl deze agent in de problemen was.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="8fc3a-943">
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-944">Op Access</span><span class="sxs-lookup"><span data-stu-id="8fc3a-944">On Access</span></span></li>
<li><span data-ttu-id="8fc3a-945">IE-downloads en Outlook Express-bijlagen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8fc3a-946">Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="8fc3a-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8fc3a-947">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-948">
</dt>
<dt>Reden: De reden Microsoft Defender Antivirus realtimebeveiliging een functie opnieuw heeft gestart.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-949">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-950">De realtimebeveiligingsfunctie is opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="8fc3a-951">Als deze gebeurtenis zich opnieuw voordeed, neem dan contact op <a href="https://go.microsoft.com/fwlink/?LinkId=215491">met de technische ondersteuning van Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-952">Gebeurtenis-id: 5000</span><span class="sxs-lookup"><span data-stu-id="8fc3a-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-953">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-955">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-955">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-956">
<b>Realtime beveiliging is ingeschakeld. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-957">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-958">Microsoft Defender Antivirus in realtime beveiligingsscans voor malware en andere mogelijk ongewenste software is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-959">Gebeurtenis-id: 5001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-960">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-962">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-962">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-963">
<b>Realtimebeveiliging is uitgeschakeld. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-964">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-965">Microsoft Defender Antivirus realtime beveiligingsscan voor malware en andere mogelijk ongewenste software is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-966">Gebeurtenis-id: 5004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-967">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-969">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-969">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-970">
<b>De configuratie voor realtimebeveiliging is gewijzigd. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-971">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-972">Microsoft Defender Antivirus de configuratie van realtimebeveiligingsfunctie is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="8fc3a-973">
<dt>Functie: &lt; &gt; Functie, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="8fc3a-974">Op Access</span><span class="sxs-lookup"><span data-stu-id="8fc3a-974">On Access</span></span></li>
<li><span data-ttu-id="8fc3a-975">IE-downloads en Outlook Express-bijlagen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="8fc3a-976">Gedragscontrole</span><span class="sxs-lookup"><span data-stu-id="8fc3a-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="8fc3a-977">Netwerkcontrolesysteem</span><span class="sxs-lookup"><span data-stu-id="8fc3a-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="8fc3a-978">
</dt>
<dt>Configuratie: </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-979">Gebeurtenis-id: 5007</span><span class="sxs-lookup"><span data-stu-id="8fc3a-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-980">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-982">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-982">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-983">
<b>De configuratie van het antimalwareplatform is gewijzigd.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-984">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-985">Microsoft Defender Antivirus configuratie is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="8fc3a-986">Als dit een onverwachte gebeurtenis is, moet u de instellingen controleren, omdat dit het gevolg kan zijn van malware.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="8fc3a-987">
<dt>Oude waarde: &lt; Oud waardenummer &gt; Oude antivirusconfiguratiewaarde.</dt> 
<dt>Nieuwe waarde: &lt; Nieuw waardenummer &gt; Nieuwe antivirusconfiguratiewaarde.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-988">Gebeurtenis-id: 5008</span><span class="sxs-lookup"><span data-stu-id="8fc3a-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-989">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-991">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-991">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-992">
<b>De antimalware-engine heeft een fout ondervonden en is mislukt.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-993">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-994">Microsoft Defender Antivirus is beëindigd vanwege een onverwachte fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="8fc3a-995">
<dt>Type fout: &lt; Type fout &gt; , bijvoorbeeld: Crash of Hang</dt>Exception
<dt>Code: &lt; Foutcode &gt; </dt>
<dt>Resource: &lt; Resource: Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-996">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-997">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="8fc3a-998">Probeer de service opnieuw te starten.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="8fc3a-999">Voor antimalware, antivirus en spyware typt u bij een verhoogde opdrachtprompt <b>netstop msmpsvc</b>en typt u <b>msmpsvc netstart</b> om de antimalware-engine opnieuw te starten.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="8fc3a-1000">Typ voor het netwerkcontrolesysteem <i>,</i>bij een opdrachtprompt met verhoogde opdracht, <b>netto start nissrv</b>en typ vervolgens <b>net start nissrv</b> om de engine Netwerkcontrolesysteem opnieuw te starten met behulp van het NiSSRV.exe-bestand. <i></i></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="8fc3a-1001">Als de fout op dezelfde manier mislukt, zoekt u de foutcode op door <b></b> toegang te krijgen tot de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft-ondersteuningssite</a> en het foutnummer in te voeren in het vak Zoeken en contact op te nemen met de technische ondersteuning <a href="https://go.microsoft.com/fwlink/?LinkId=215491">van Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1002">Gebruikersactie:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1003">De Microsoft Defender Antivirus client engine is gestopt vanwege een onverwachte fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="8fc3a-1004">Problemen met deze gebeurtenis oplossen:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="8fc3a-1005">Voer de scan opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="8fc3a-1006">Als het op dezelfde manier mislukt, gaat u naar de <b></b> <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-site</a>en voert u het foutnummer in het vak Zoeken in om te zoeken naar de foutcode.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="8fc3a-1007">Contact opnemen met <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft technische ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1008">Gebeurtenis-id: 5009</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1009">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1011">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1012">
<b>Scannen op malware en andere mogelijk ongewenste software is ingeschakeld. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1013">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1014">Microsoft Defender Antivirus scannen op malware en andere mogelijk ongewenste software is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1015">Gebeurtenis-id: 5010</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1016">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1018">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1019">
<b>Scannen op malware en andere mogelijk ongewenste software is uitgeschakeld.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1020">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1021">Microsoft Defender Antivirus scannen op malware en andere mogelijk ongewenste software is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1022">Gebeurtenis-id: 5011</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1023">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1025">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1026">
<b>Scannen naar virussen is ingeschakeld.</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1027">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1028">Microsoft Defender Antivirus scannen op virussen is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1029">Gebeurtenis-id: 5012</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1030">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1032">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1033">
<b>Het scannen van virussen is uitgeschakeld. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1034">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1035">Microsoft Defender Antivirus scannen op virussen is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1036">Gebeurtenis-id: 5100</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1037">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1039">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1040">
<b>Het antimalwareplatform verloopt binnenkort. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1041">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1042">Microsoft Defender Antivirus heeft een respijtperiode ingevoerd en verloopt binnenkort.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="8fc3a-1043">Na verloop van tijd schakelt dit programma de beveiliging tegen virussen, spyware en andere mogelijk ongewenste software uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="8fc3a-1044">
<dt>Vervaldatum: De reden waarom Microsoft Defender Antivirus verloopt.</dt> 
<dt>Vervaldatum: De datum waarop Microsoft Defender Antivirus verloopt.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1045">Gebeurtenis-id: 5101</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="8fc3a-1046">Symbolische naam:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1048">Bericht:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="8fc3a-1049">
<b>Het antimalware-platform is verlopen. </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1050">Beschrijving:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="8fc3a-1051">Microsoft Defender Antivirus respijtperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="8fc3a-1052">Beveiliging tegen virussen, spyware en andere mogelijk ongewenste software is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="8fc3a-1053">
<dt>Vervaldatum: vervaldatum:</dt>
<dt> </dt> 
<dt>foutcode: &lt; foutcode &gt; Resultaatcode gekoppeld aan bedreigingsstatus. Standaard HRESULT-waarden.</dt> 
<dt>Foutbeschrijving: &lt; Foutbeschrijving &gt; Beschrijving van de fout.</dt>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="8fc3a-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivirus clientfoutcodes als Microsoft Defender Antivirus problemen krijgt, krijgt u meestal een foutcode om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="8fc3a-1055">Meestal betekent een fout dat er een probleem is opgetreden bij het installeren van een update.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="8fc3a-1056">In deze sectie vindt u de volgende informatie over Microsoft Defender Antivirus clientfouten.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="8fc3a-1057">-   De foutcode -   De mogelijke reden voor de fout Advies over wat u nu moet -   doen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="8fc3a-1058">Gebruik de informatie in deze tabellen om problemen met foutcodes Microsoft Defender Antivirus oplossen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1059">Foutcode: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-1060">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1060">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1062">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="8fc3a-1063">Deze fout geeft aan dat u mogelijk geen geheugen meer hebt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="8fc3a-1064">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="8fc3a-1065">Controleer het beschikbare geheugen op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="8fc3a-1066">Sluit ongebruikte toepassingen die worden uitgevoerd om geheugen vrij te maken op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="8fc3a-1067">Start het apparaat opnieuw op en voer de scan opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1068">Foutcode: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="8fc3a-1069">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1069">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1071">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1072">Deze fout geeft aan dat er mogelijk een probleem is met uw beveiligingsproduct.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="8fc3a-1073">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="8fc3a-1074">Werk de definities bij.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1074">Update the definitions.</span></span> <span data-ttu-id="8fc3a-1075">Een van de volgende:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1075">Either:</span></span><ol>
<li><span data-ttu-id="8fc3a-1076">Klik op <b>de knop Definities</b> bijwerken op het <b>tabblad Bijwerken</b> in Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="8fc3a-1077">Of:</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1077">Or,</span></span>
</li>
<li><span data-ttu-id="8fc3a-1078">Download de meest recente definities van <a href="https://aka.ms/wdsi">de Microsoft-beveiligingsinformatie site.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="8fc3a-1079">Opmerking: De grootte van het definitiebestand dat van de site is gedownload, kan groter zijn dan 60 MB en mag niet worden gebruikt als een langetermijnoplossing voor het bijwerken van definities.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="8fc3a-1080">Voer een volledige scan uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="8fc3a-1081">Start het apparaat opnieuw en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1082">Foutcode: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="8fc3a-1083">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1083">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1085">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1086">Deze fout geeft aan dat er mogelijk een motorconfiguratiefout is opgetreden. meestal is dit gerelateerd aan invoergegevens waardoor de engine niet goed kan functioneren.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1087">Foutcode: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1088">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1088">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1090">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1091">Deze fout geeft aan dat Microsoft Defender Antivirus bedreiging niet in quarantaine kan plaatsen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1092">Foutcode: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1093">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1093">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1095">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1096">Deze fout geeft aan dat een herstart vereist is om het verwijderen van bedreigingen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="8fc3a-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1098">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1098">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1100">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1101">Deze fout geeft aan dat de bedreiging mogelijk niet meer aanwezig is op de media, of dat malware u kan stoppen met het scannen van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="8fc3a-1102">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="8fc3a-1103">Voer de <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft-beveiligingsscanner</a> vervolgens uw beveiligingssoftware bij en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1104">Foutcode: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="8fc3a-1105">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1105">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1107">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1108">Deze fout geeft aan dat een volledige systeemscan mogelijk is vereist.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="8fc3a-1109">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1109">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1110">Voer een volledige systeemscan uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1111">Foutcode: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1112">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1112">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1114">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1115">Deze fout geeft aan dat handmatige stappen nodig zijn om het verwijderen van bedreigingen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1116">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1116">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1117">Volg de handmatige herstelstappen die worden beschreven in de <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="8fc3a-1118">U kunt een bedreigingsspecifieke koppeling vinden in de gebeurtenisgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1119">Foutcode: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1120">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1120">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1122">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1123">Deze fout geeft aan dat verwijdering binnen het containertype mogelijk niet wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1124">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1124">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1125">Microsoft Defender Antivirus is niet in staat om gedetecteerde bedreigingen in het archief te herstellen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="8fc3a-1126">U kunt de gedetecteerde resources handmatig verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1127">Foutcode: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1128">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1128">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1130">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1131">Deze fout geeft aan dat het verwijderen van lage en gemiddelde bedreigingen mogelijk is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1132">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1132">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1133">Controleer de gedetecteerde bedreigingen en los ze zo nodig op.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1134">Foutcode: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1135">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1135">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1137">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1138">Deze fout geeft aan dat u de bedreiging opnieuw moet scannen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1139">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1139">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1140">Voer een volledige systeemscan uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1141">Foutcode: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1142">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1142">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="8fc3a-1144">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1145">Deze fout geeft aan dat een offlinescan vereist is.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1146">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1146">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1147">Offline uitvoeren Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="8fc3a-1148">U kunt lezen hoe u dit doet in het offline Microsoft Defender Antivirus <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">artikel.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="8fc3a-1149">Foutcode: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="8fc3a-1150">Bericht</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1150">Message</span></span></td>
<td><span data-ttu-id="8fc3a-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="8fc3a-1152">Mogelijke reden</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="8fc3a-1153">Deze fout geeft aan dat Microsoft Defender Antivirus de huidige versie van het platform niet ondersteunt en een nieuwe versie van het platform vereist.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="8fc3a-1154">Oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1154">Resolution</span></span></td><td>
<span data-ttu-id="8fc3a-1155">U kunt alleen Microsoft Defender Antivirus in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="8fc3a-1156">Voor Windows 8, Windows 7 en Windows Vista kunt u <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection.</a></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="8fc3a-1157">

<a id="internal-error-codes"></a>De volgende foutcodes worden gebruikt tijdens interne tests van Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="8fc3a-1158">Als u deze fouten ziet, kunt u proberen definities [bij te](manage-updates-baselines-microsoft-defender-antivirus.md) werken en een rescan rechtstreeks op het eindpunt af te dwingen.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="8fc3a-1159">Interne foutcodes</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="8fc3a-1160"><b>Foutcode</b></span><span class="sxs-lookup"><span data-stu-id="8fc3a-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="8fc3a-1161">Bericht weergegeven</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1161">Message displayed</span></span></th>
<th><span data-ttu-id="8fc3a-1162">Mogelijke reden voor fout en oplossing</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="8fc3a-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-1165">Controleer uw internetverbinding en voer de scan opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="8fc3a-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="8fc3a-1168">Dit is een interne fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1168">This is an internal error.</span></span> <span data-ttu-id="8fc3a-1169">De oorzaak is niet duidelijk gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="8fc3a-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="8fc3a-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="8fc3a-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="8fc3a-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="8fc3a-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="8fc3a-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="8fc3a-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="8fc3a-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="8fc3a-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="8fc3a-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="8fc3a-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="8fc3a-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="8fc3a-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="8fc3a-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="8fc3a-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="8fc3a-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="8fc3a-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="8fc3a-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="8fc3a-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="8fc3a-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="8fc3a-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="8fc3a-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="8fc3a-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="8fc3a-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="8fc3a-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="8fc3a-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="8fc3a-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="8fc3a-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="8fc3a-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="8fc3a-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="8fc3a-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="8fc3a-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="8fc3a-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="8fc3a-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-1238">Dit is een interne fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1238">This is an internal error.</span></span> <span data-ttu-id="8fc3a-1239">Het kan worden geactiveerd wanneer het verwijderen van malware niet is gelukt.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="8fc3a-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="8fc3a-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="8fc3a-1242">Dit is een interne fout.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1242">This is an internal error.</span></span> <span data-ttu-id="8fc3a-1243">Het kan zijn geactiveerd wanneer een scan niet kan worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="8fc3a-1244">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1244">Related topics</span></span>

- [<span data-ttu-id="8fc3a-1245">Rapport over Microsoft Defender Antivirusbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8fc3a-1246">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8fc3a-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)