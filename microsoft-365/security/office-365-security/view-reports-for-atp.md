---
title: Rapporten weergeven voor Defender voor Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Rapporten voor Microsoft Defender voor Office 365 zoeken en gebruiken in het beveiligings &amp; compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8885eea2168cc40c497f6fa1066ae020dda7fd7c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087707"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="2e72e-103">Rapporten weergeven voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2e72e-104">Bedrijven van Microsoft Defender voor Office 365 (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365-abonnement 1 of Microsoft Defender voor Office 365 abonnement 2-uitbreidingen) bevatten diverse beveiligingsrapporten.</span><span class="sxs-lookup"><span data-stu-id="2e72e-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="2e72e-105">Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)hebt, kunt u deze rapporten weergeven in het compliance-beveiligings & door **Reports** naar het \> **Dashboard** rapporten te gaan.</span><span class="sxs-lookup"><span data-stu-id="2e72e-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="2e72e-106">Open om rechtstreeks naar het Dashboard rapporten te gaan <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="2e72e-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Het Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="2e72e-108">Rapport over bestandstypen voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="2e72e-109">In het rapport met het **rapport bestandstypen voor 365 van** wordt weergegeven welk type bestanden als schadelijk voor [veilige bijlagen](atp-safe-attachments.md)is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="2e72e-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="2e72e-110">De geaggregeerde weergave van het rapport mag 90 dagen filteren, terwijl de detailweergave alleen 10 dagen van filteren toestaat.</span><span class="sxs-lookup"><span data-stu-id="2e72e-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="2e72e-111">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de **bestandstypen voor Defender voor Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="2e72e-112">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="2e72e-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget voor Office 365-bestandstypen in het Dashboard rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="2e72e-114">De informatie in dit rapport is ook beschikbaar in het rapport voor het wijzigen van het bericht in de [Defender for Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="2e72e-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="2e72e-115">Rapportweergave voor het rapport van het bestandstype voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="2e72e-116">De volgende weergaven zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2e72e-116">The following views are available:</span></span>

- <span data-ttu-id="2e72e-117">**Gegevens weergeven op: bestand**: de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="2e72e-118">**Schadelijke Excel-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="2e72e-119">**Schadelijke Flash-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="2e72e-120">**Schadelijke PDF-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="2e72e-121">**Schadelijke PowerPoint-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="2e72e-122">**Schadelijke Url's**</span><span class="sxs-lookup"><span data-stu-id="2e72e-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="2e72e-123">**Schadelijke Word-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="2e72e-124">**Schadelijke bijlagen met uitvoerbaar bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="2e72e-125">**Gezien**</span><span class="sxs-lookup"><span data-stu-id="2e72e-125">**Others**</span></span>

  <span data-ttu-id="2e72e-126">Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2e72e-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="2e72e-128">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-129">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-130">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="2e72e-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="2e72e-131">**Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="2e72e-132">**Toegang blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2e72e-132">**Block access**</span></span>
  - <span data-ttu-id="2e72e-133">**Berichten vervangen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-133">**Messages replaced**</span></span>
  - <span data-ttu-id="2e72e-134">**Berichten gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="2e72e-134">**Messages monitored**</span></span>
  - <span data-ttu-id="2e72e-135">**Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e72e-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="2e72e-137">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-138">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-139">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="2e72e-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="2e72e-140">De tabel weergave Details voor het rapport voor de bestandsindelingen voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="2e72e-141">Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="2e72e-142">Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="2e72e-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2e72e-143">**Gegevens uit een bestand weergeven**:</span><span class="sxs-lookup"><span data-stu-id="2e72e-143">**View data by: File**:</span></span>

  - <span data-ttu-id="2e72e-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-144">**Date**</span></span>
  - <span data-ttu-id="2e72e-145">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="2e72e-145">**Recipient address**</span></span>
  - <span data-ttu-id="2e72e-146">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2e72e-146">**Sender address**</span></span>
  - <span data-ttu-id="2e72e-147">**Bericht-id**: beschikbaar in het veld **bericht-id-** header in de berichtkop en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="2e72e-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="2e72e-148">Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).</span><span class="sxs-lookup"><span data-stu-id="2e72e-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="2e72e-149">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-149">**File**</span></span>

  <span data-ttu-id="2e72e-150">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-151">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-152">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="2e72e-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="2e72e-153">**Gegevens weergeven op: bericht**:</span><span class="sxs-lookup"><span data-stu-id="2e72e-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="2e72e-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-154">**Date**</span></span>
  - <span data-ttu-id="2e72e-155">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="2e72e-155">**Recipient address**</span></span>
  - <span data-ttu-id="2e72e-156">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2e72e-156">**Sender address**</span></span>
  - <span data-ttu-id="2e72e-157">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="2e72e-157">**Message ID**</span></span>
  - <span data-ttu-id="2e72e-158">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-158">**File**</span></span>
  - <span data-ttu-id="2e72e-159">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="2e72e-159">**Subject**</span></span>

  <span data-ttu-id="2e72e-160">Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2e72e-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="2e72e-161">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-162">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="2e72e-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="2e72e-163">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="2e72e-164">Rapport over berichtverwerking voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="2e72e-165">In het rapport vrije voorkeuren voor **ATP-berichten** ziet u de acties die zijn ondernomen voor e-mailberichten die zijn gevonden met schadelijke inhoud.</span><span class="sxs-lookup"><span data-stu-id="2e72e-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="2e72e-166">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **Defender for Office 365 bericht dispositioning**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="2e72e-167">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="2e72e-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![De widget voor Office 365 voor het verplaatsen van berichten in het Dashboard rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="2e72e-169">De informatie in dit rapport is ook beschikbaar in het [rapport met bestandstypen van de Defender voor Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="2e72e-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="2e72e-170">Rapportweergave voor het rapport over het wijzigen van de berichten voor de Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="2e72e-171">De volgende weergaven zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2e72e-171">The following views are available:</span></span>

- <span data-ttu-id="2e72e-172">**Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="2e72e-173">**Toegang blokkeren**</span><span class="sxs-lookup"><span data-stu-id="2e72e-173">**Block access**</span></span>
  - <span data-ttu-id="2e72e-174">**Berichten vervangen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-174">**Messages replaced**</span></span>
  - <span data-ttu-id="2e72e-175">**Berichten gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="2e72e-175">**Messages monitored**</span></span>
  - <span data-ttu-id="2e72e-176">**Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e72e-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="2e72e-178">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-179">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-180">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="2e72e-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="2e72e-181">**Gegevens weergeven op: bestand**: de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="2e72e-182">**Schadelijke Excel-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="2e72e-183">**Schadelijke Flash-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="2e72e-184">**Schadelijke PDF-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="2e72e-185">**Schadelijke PowerPoint-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="2e72e-186">**Schadelijke Url's**</span><span class="sxs-lookup"><span data-stu-id="2e72e-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="2e72e-187">**Schadelijke Word-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="2e72e-188">**Schadelijke bijlagen met uitvoerbaar bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="2e72e-189">**Gezien**</span><span class="sxs-lookup"><span data-stu-id="2e72e-189">**Others**</span></span>

  <span data-ttu-id="2e72e-190">Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2e72e-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="2e72e-192">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-193">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-194">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="2e72e-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="2e72e-195">Weergave Details van het bericht voor het wijzigen van de weergave van het bericht voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e72e-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="2e72e-196">Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="2e72e-197">Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="2e72e-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2e72e-198">**Gegevens weergeven op: bericht**:</span><span class="sxs-lookup"><span data-stu-id="2e72e-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="2e72e-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-199">**Date**</span></span>
  - <span data-ttu-id="2e72e-200">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="2e72e-200">**Recipient address**</span></span>
  - <span data-ttu-id="2e72e-201">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2e72e-201">**Sender address**</span></span>
  - <span data-ttu-id="2e72e-202">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="2e72e-202">**Message ID**</span></span>
  - <span data-ttu-id="2e72e-203">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-203">**File**</span></span>
  - <span data-ttu-id="2e72e-204">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="2e72e-204">**Subject**</span></span>

  <span data-ttu-id="2e72e-205">Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2e72e-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="2e72e-206">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-207">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="2e72e-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="2e72e-208">**Gegevens uit een bestand weergeven**:</span><span class="sxs-lookup"><span data-stu-id="2e72e-208">**View data by: File**:</span></span>

  - <span data-ttu-id="2e72e-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-209">**Date**</span></span>
  - <span data-ttu-id="2e72e-210">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="2e72e-210">**Recipient address**</span></span>
  - <span data-ttu-id="2e72e-211">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2e72e-211">**Sender address**</span></span>
  - <span data-ttu-id="2e72e-212">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="2e72e-212">**Message ID**</span></span>
  - <span data-ttu-id="2e72e-213">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="2e72e-213">**File**</span></span>

  <span data-ttu-id="2e72e-214">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-215">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-216">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="2e72e-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="2e72e-217">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="2e72e-218">Rapport over e-mail latentie</span><span class="sxs-lookup"><span data-stu-id="2e72e-218">Mail latency report</span></span>

<span data-ttu-id="2e72e-219">In het **rapport e-mail latentie** ziet u een geaggregeerde weergave van de bezorgings latentie en de detonatie latentie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e72e-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="2e72e-220">De levertijden voor e-mail in de service zijn van invloed op een aantal factoren en de absolute bezorgings tijd in seconden is vaak geen goede indicatie van het succes of een probleem.</span><span class="sxs-lookup"><span data-stu-id="2e72e-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="2e72e-221">Een traag tijdstip van levering op één dag wordt mogelijk beschouwd als een gemiddelde levertijd op een andere dag, of omgekeerd.</span><span class="sxs-lookup"><span data-stu-id="2e72e-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="2e72e-222">In het **rapport e-mail latentie** wordt geprobeerd berichten te bezorgen op basis van statistische gegevens over de waargenomen bezorgings tijden van andere berichten:</span><span class="sxs-lookup"><span data-stu-id="2e72e-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="2e72e-223">**50e percentiel**: dit is het middelste punt voor de bezorgings tijd van berichten.</span><span class="sxs-lookup"><span data-stu-id="2e72e-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="2e72e-224">U kunt deze waarde als gemiddelde bezorgings tijd beschouwen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="2e72e-225">**negentigste percentiel**: Hiermee wordt een hoge latentie aangegeven voor de bezorging van berichten.</span><span class="sxs-lookup"><span data-stu-id="2e72e-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="2e72e-226">Slechts 10% van de berichten duurde langer dan de waarde voor levering.</span><span class="sxs-lookup"><span data-stu-id="2e72e-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="2e72e-227">**99th percentiel**: Hiermee wordt de beste latentie voor de bezorging van berichten aangegeven.</span><span class="sxs-lookup"><span data-stu-id="2e72e-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="2e72e-228">De client-en netwerklatentie zijn niet opgenomen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="2e72e-229">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport e-mail latentie**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="2e72e-230">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="2e72e-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget e-mail latentie rapporten in het Dashboard rapporten](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="2e72e-232">Rapportweergave voor het rapport latentie van e-mail latentie</span><span class="sxs-lookup"><span data-stu-id="2e72e-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="2e72e-233">Wanneer u het rapport opent, wordt standaard het tabblad **50e percentiel** geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2e72e-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="2e72e-234">Deze weergave bevat standaard een grafiek die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2e72e-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="2e72e-235">**Datum**: de laatste 7 dagen</span><span class="sxs-lookup"><span data-stu-id="2e72e-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="2e72e-236">**Berichtenweergave**:</span><span class="sxs-lookup"><span data-stu-id="2e72e-236">**Message View**:</span></span>
  - <span data-ttu-id="2e72e-237">Detonatie berichten</span><span class="sxs-lookup"><span data-stu-id="2e72e-237">Detonated messages</span></span>

<span data-ttu-id="2e72e-238">In dit diagram ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="2e72e-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="2e72e-239">**E-mail bezorgings latentie**</span><span class="sxs-lookup"><span data-stu-id="2e72e-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="2e72e-240">**Detonatie latentie**</span><span class="sxs-lookup"><span data-stu-id="2e72e-240">**Detonation latency**</span></span>

<span data-ttu-id="2e72e-241">Wanneer u de muisaanwijzer boven een categorie in de grafiek houdt, ziet u een uitsplitsing van de latentie in elke categorie.</span><span class="sxs-lookup"><span data-stu-id="2e72e-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Rapport over e-mail latentie](../../media/mail-latency-report.png)

<span data-ttu-id="2e72e-243">Als u op **filter** in de rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2e72e-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2e72e-244">Alle berichten</span><span class="sxs-lookup"><span data-stu-id="2e72e-244">All messages</span></span>
- <span data-ttu-id="2e72e-245">Berichten die bijlagen of Url's bevatten</span><span class="sxs-lookup"><span data-stu-id="2e72e-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="2e72e-246">Als u op het tabblad **negentigste percentielen** of het tabblad **99th percentiel** wordt geklikt, worden dezelfde standaardfilters uit de weergave **50e percentiel** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2e72e-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="2e72e-247">Weergave Details van het rapport met e-mail latentie</span><span class="sxs-lookup"><span data-stu-id="2e72e-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="2e72e-248">De volgende informatie wordt weergegeven in de tabel weergave Details:</span><span class="sxs-lookup"><span data-stu-id="2e72e-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="2e72e-249">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-249">**Date**</span></span>
- <span data-ttu-id="2e72e-250">**Waarden liggen tussen**</span><span class="sxs-lookup"><span data-stu-id="2e72e-250">**Percentiles**</span></span>
- <span data-ttu-id="2e72e-251">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="2e72e-251">**Message count**</span></span>
- <span data-ttu-id="2e72e-252">**Totale latentie**</span><span class="sxs-lookup"><span data-stu-id="2e72e-252">**Overall latency**</span></span>

![Details van e-mail latentie rapporten](../../media/mail-latency-report-details.png)

<span data-ttu-id="2e72e-254">In het voorgaande wordt aangegeven dat het gemiddelde latentie van alle verzonden en deliete berichten **108,033** seconden is gedurende 2 november.</span><span class="sxs-lookup"><span data-stu-id="2e72e-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="2e72e-255">De tabel Details bevat dezelfde informatie op elk tabblad.</span><span class="sxs-lookup"><span data-stu-id="2e72e-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="2e72e-256">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="2e72e-256">Threat protection status report</span></span>

<span data-ttu-id="2e72e-257">Het rapport **status van bedreigingsbeveiliging** is één weergave waarin informatie wordt verzameld over schadelijke inhoud en ongewenste E-mail die wordt gedetecteerd en geblokkeerd via [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e72e-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="2e72e-258">Zie [statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e72e-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="2e72e-259">Rapport over URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2e72e-259">URL threat protection report</span></span>

<span data-ttu-id="2e72e-260">Het **rapport URL Threat Protection** biedt samenvattings-en trend weergaven voor bedreigingen die worden gedetecteerd en acties die worden uitgevoerd op URL-klikken als onderdeel van [veilige koppelingen](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="2e72e-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="2e72e-261">Dit rapport hoeft niet te klikken op gegevens van gebruikers waar voor het beleid voor veilige koppelingen de optie **gebruiker niet bijhouden** is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2e72e-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="2e72e-262">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport URL-beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="2e72e-263">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="2e72e-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![De widget URL-beveiligingsrapport in het Dashboard rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="2e72e-265">Dit is een *beveiligingsrapport* voor trends, wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="2e72e-266">De gegevens in de samengevoegde weergave zijn daardoor niet in realtime beschikbaar, maar de gegevens in de tabel weergave Details is dus een lichte discrepantie tussen de twee weergaven.</span><span class="sxs-lookup"><span data-stu-id="2e72e-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="2e72e-267">Rapportweergave voor het rapport URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2e72e-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="2e72e-268">Het rapport **URL Threat Protection** heeft twee geaggregeerde weergaven die elke vier uur worden vernieuwd met de gegevens voor de laatste 90 dagen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="2e72e-269">**URL klik op beschermings actie**: toont het aantal gebruikers in de organisatie op basis van de URL en de resultaten van de Klik op:</span><span class="sxs-lookup"><span data-stu-id="2e72e-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="2e72e-270">**Geblokkeerd** (de gebruiker is geblokkeerd voor het navigeren naar de URL)</span><span class="sxs-lookup"><span data-stu-id="2e72e-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="2e72e-271">**Geblokkeerde en geklikt door**</span><span class="sxs-lookup"><span data-stu-id="2e72e-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="2e72e-272">**Door de scan geklikt**</span><span class="sxs-lookup"><span data-stu-id="2e72e-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="2e72e-273">Met een klik wordt aangegeven dat de gebruiker heeft geklikt op de blok pagina voor de schadelijke website (beheerders kunnen de klik-en-beleidsregels uitschakelen in beleidsregels voor veilige koppelingen).</span><span class="sxs-lookup"><span data-stu-id="2e72e-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="2e72e-274">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-275">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-276">De beschikbare klikken op beschermings acties plus de **toegestane** waarde (de gebruiker heeft de mogelijkheid om naar de URL te gaan).</span><span class="sxs-lookup"><span data-stu-id="2e72e-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL klik op beschermings actie weergave in het rapport URL Threat Protection](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="2e72e-278">**URL klik op toepassing**: hier ziet u het aantal te klikken voor de URL door toepassingen die ondersteuning bieden voor veilige koppelingen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="2e72e-279">**E-mailclient**</span><span class="sxs-lookup"><span data-stu-id="2e72e-279">**Email client**</span></span>
  - <span data-ttu-id="2e72e-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="2e72e-280">**PowerPoint**</span></span>
  - <span data-ttu-id="2e72e-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="2e72e-281">**Word**</span></span>
  - <span data-ttu-id="2e72e-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="2e72e-282">**Excel**</span></span>
  - <span data-ttu-id="2e72e-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="2e72e-283">**OneNote**</span></span>
  - <span data-ttu-id="2e72e-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="2e72e-284">**Visio**</span></span>
  - <span data-ttu-id="2e72e-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="2e72e-285">**Teams**</span></span>
  - <span data-ttu-id="2e72e-286">**Overige**</span><span class="sxs-lookup"><span data-stu-id="2e72e-286">**Other**</span></span>

  <span data-ttu-id="2e72e-287">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="2e72e-288">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="2e72e-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="2e72e-289">De beschikbare toepassingen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="2e72e-290">Weergave Details van het rapport URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2e72e-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="2e72e-291">Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die binnen de organisatie plaatsvinden voor de laatste 7 dagen, met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="2e72e-292">**Klik op tijd**</span><span class="sxs-lookup"><span data-stu-id="2e72e-292">**Click time**</span></span>
- <span data-ttu-id="2e72e-293">**Gebruiker**</span><span class="sxs-lookup"><span data-stu-id="2e72e-293">**User**</span></span>
- <span data-ttu-id="2e72e-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="2e72e-294">**URL**</span></span>
- <span data-ttu-id="2e72e-295">**Actierij**</span><span class="sxs-lookup"><span data-stu-id="2e72e-295">**Action**</span></span>
- <span data-ttu-id="2e72e-296">**App**</span><span class="sxs-lookup"><span data-stu-id="2e72e-296">**App**</span></span>

<span data-ttu-id="2e72e-297">Als u in de weergave Details op **filters** klikt, kunt u filteren op dezelfde criteria als in de rapportweergave, en ook op **domeinen** of **geadresseerden** , gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="2e72e-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="2e72e-298">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="2e72e-299">Extra rapporten om weer te geven</span><span class="sxs-lookup"><span data-stu-id="2e72e-299">Additional reports to view</span></span>

<span data-ttu-id="2e72e-300">Naast de rapporten die in dit onderwerp worden beschreven, zijn er nog enkele andere rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="2e72e-300">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="2e72e-301">Rapport</span><span class="sxs-lookup"><span data-stu-id="2e72e-301">Report</span></span>|<span data-ttu-id="2e72e-302">Rond</span><span class="sxs-lookup"><span data-stu-id="2e72e-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="2e72e-303">**Explorer** (Microsoft Defender voor Office 365 abonnement 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="2e72e-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="2e72e-304">Bedreigingsverkenner (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="2e72e-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="2e72e-305">**Beveiligingsrapporten voor e-mail**, zoals het rapport belangrijkste afzenders en geadresseerden, het rapport spoofberichten en het rapport detectie van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="2e72e-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="2e72e-306">Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="2e72e-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="2e72e-307">**E-mail stroom rapporten**, zoals het doorsturen van rapporten, het rapport status van de mail stroom en het rapport meest voorkomende afzenders en geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2e72e-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="2e72e-308">De e-mail stroom rapporten weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="2e72e-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="2e72e-309">**URL-tracering voor veilige koppelingen** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="2e72e-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="2e72e-310">De uitvoer van deze cmdlet toont u de resultaten van acties van veilige koppelingen in de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="2e72e-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="2e72e-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="2e72e-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="2e72e-312">**Resultaten van e-mail verkeer voor EOP en Microsoft Defender voor Office 365** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="2e72e-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="2e72e-313">De uitvoer van deze cmdlet bevat informatie over domein, datum, evenement type, richting, actie en aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="2e72e-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="2e72e-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="2e72e-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="2e72e-315">**E-mail detailrapporten voor EOP en Defender voor Office 365 detectie** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="2e72e-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="2e72e-316">De uitvoer van deze cmdlet bevat details over schadelijke bestanden of Url's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.</span><span class="sxs-lookup"><span data-stu-id="2e72e-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="2e72e-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="2e72e-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="2e72e-318">Welke machtigingen zijn vereist voor het weergeven van de rapporten van de Defender for Office 365?</span><span class="sxs-lookup"><span data-stu-id="2e72e-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="2e72e-319">Voor het weergeven en gebruiken van de rapporten die in dit onderwerp worden beschreven, **moet u beschikken over de juiste rol die is toegewezen aan het beveiligings &amp; compliance en het Beheercentrum van Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2e72e-319">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="2e72e-320">Voor het beveiligings & nalevings centrum moet een van de volgende rollen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="2e72e-320">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="2e72e-321">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="2e72e-321">Organization Management</span></span>
  - <span data-ttu-id="2e72e-322">Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="2e72e-322">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="2e72e-323">Beveiligings operator (dit kan worden toegewezen in het Azure Active Directory-beheercentrum [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="2e72e-323">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="2e72e-324">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="2e72e-324">Security Reader</span></span>

- <span data-ttu-id="2e72e-325">Voor Exchange Online moet u beschikken over een van de volgende rollen die zijn toegewezen in het Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="2e72e-325">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="2e72e-326">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="2e72e-326">Organization Management</span></span>
  - <span data-ttu-id="2e72e-327">Organisatiebeheer alleen weergeven</span><span class="sxs-lookup"><span data-stu-id="2e72e-327">View-only Organization Management</span></span>
  - <span data-ttu-id="2e72e-328">Rollen View-Only geadresseerden</span><span class="sxs-lookup"><span data-stu-id="2e72e-328">View-Only Recipients role</span></span>
  - <span data-ttu-id="2e72e-329">Nalevings beheer</span><span class="sxs-lookup"><span data-stu-id="2e72e-329">Compliance Management</span></span>

<span data-ttu-id="2e72e-330">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="2e72e-330">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="2e72e-331">Machtigingen in het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="2e72e-331">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="2e72e-332">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2e72e-332">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="2e72e-333">Wat moet ik doen als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="2e72e-333">What if the reports aren't showing data?</span></span>

<span data-ttu-id="2e72e-334">Als u geen gegevens ziet in uw 365-rapporten van Defender for Office, controleert u of uw beleidsregels correct zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="2e72e-334">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="2e72e-335">Als u wilt dat de beveiliging van Defender voor Office 365 op de juiste plek is geconfigureerd, moet uw organisatie beleidsregels voor [veilige koppelingen](set-up-atp-safe-links-policies.md) en een beleid voor veilige [bijlagen](set-up-atp-safe-attachments-policies.md) definiëren.</span><span class="sxs-lookup"><span data-stu-id="2e72e-335">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="2e72e-336">Zie ook [antispam en bescherming tegen malware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2e72e-336">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e72e-337">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2e72e-337">Related topics</span></span>

[<span data-ttu-id="2e72e-338">Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="2e72e-338">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="2e72e-339">Rolmachtigingen (Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="2e72e-339">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
