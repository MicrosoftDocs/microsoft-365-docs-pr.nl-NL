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
ms.openlocfilehash: b24249bcbba60bc5340d973567369f534a0178fb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842914"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="fc769-103">Rapporten weergeven voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fc769-104">Bedrijven van Microsoft Defender voor Office 365 (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365-abonnement 1 of Microsoft Defender voor Office 365 abonnement 2-uitbreidingen) bevatten diverse beveiligingsrapporten.</span><span class="sxs-lookup"><span data-stu-id="fc769-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="fc769-105">Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)hebt, kunt u deze rapporten weergeven in het compliance-beveiligings & door **Reports** naar het \> **Dashboard** rapporten te gaan.</span><span class="sxs-lookup"><span data-stu-id="fc769-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fc769-106">Open om rechtstreeks naar het Dashboard rapporten te gaan <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="fc769-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Het Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="fc769-108">Rapport met bestandstypen voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="fc769-109">In het rapport met het **rapport bestandstypen voor 365 van** wordt weergegeven welk type bestanden als schadelijk voor [veilige bijlagen](atp-safe-attachments.md)is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="fc769-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="fc769-110">De geaggregeerde weergave van het rapport mag 90 dagen filteren, terwijl de detailweergave alleen 10 dagen van filteren toestaat.</span><span class="sxs-lookup"><span data-stu-id="fc769-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="fc769-111">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de **bestandstypen voor Defender voor Office 365**.</span><span class="sxs-lookup"><span data-stu-id="fc769-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="fc769-112">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="fc769-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget voor Office 365-bestandstypen in het Dashboard rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fc769-114">De informatie in dit rapport is ook beschikbaar in het rapport voor het wijzigen van het bericht in de [Defender for Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="fc769-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="fc769-115">Rapportweergave voor het rapport van het bestandstype voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="fc769-116">De volgende weergaven zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="fc769-116">The following views are available:</span></span>

- <span data-ttu-id="fc769-117">**Gegevens weergeven op: bestand** : de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-117">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fc769-118">**Schadelijke Excel-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fc769-119">**Schadelijke Flash-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fc769-120">**Schadelijke PDF-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fc769-121">**Schadelijke PowerPoint-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fc769-122">**Schadelijke Url's**</span><span class="sxs-lookup"><span data-stu-id="fc769-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="fc769-123">**Schadelijke Word-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fc769-124">**Schadelijke bijlagen met uitvoerbaar bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fc769-125">**Gezien**</span><span class="sxs-lookup"><span data-stu-id="fc769-125">**Others**</span></span>

  <span data-ttu-id="fc769-126">Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fc769-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fc769-128">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-128">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-129">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-130">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="fc769-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fc769-131">**Gegevens weergeven op: bericht** : de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-131">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fc769-132">**Toegang blokkeren**</span><span class="sxs-lookup"><span data-stu-id="fc769-132">**Block access**</span></span>
  - <span data-ttu-id="fc769-133">**Berichten vervangen**</span><span class="sxs-lookup"><span data-stu-id="fc769-133">**Messages replaced**</span></span>
  - <span data-ttu-id="fc769-134">**Berichten gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="fc769-134">**Messages monitored**</span></span>
  - <span data-ttu-id="fc769-135">**Vervangen door dynamische e-mail bezorging** : Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fc769-135">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fc769-137">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-137">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-138">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-139">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="fc769-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="fc769-140">De tabel weergave Details voor het rapport voor de bestandsindelingen voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="fc769-141">Als u klikt op **Details tabel weergeven** , biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen.</span><span class="sxs-lookup"><span data-stu-id="fc769-141">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fc769-142">Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="fc769-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fc769-143">**Gegevens uit een bestand weergeven** :</span><span class="sxs-lookup"><span data-stu-id="fc769-143">**View data by: File** :</span></span>

  - <span data-ttu-id="fc769-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fc769-144">**Date**</span></span>
  - <span data-ttu-id="fc769-145">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="fc769-145">**Recipient address**</span></span>
  - <span data-ttu-id="fc769-146">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="fc769-146">**Sender address**</span></span>
  - <span data-ttu-id="fc769-147">**Bericht-id** : beschikbaar in het veld **bericht-id-** header in de berichtkop en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="fc769-147">**Message ID** : Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="fc769-148">Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).</span><span class="sxs-lookup"><span data-stu-id="fc769-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="fc769-149">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-149">**File**</span></span>

  <span data-ttu-id="fc769-150">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-150">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-151">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-152">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="fc769-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fc769-153">**Gegevens weergeven op: bericht** :</span><span class="sxs-lookup"><span data-stu-id="fc769-153">**View data by: Message** :</span></span>

  - <span data-ttu-id="fc769-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fc769-154">**Date**</span></span>
  - <span data-ttu-id="fc769-155">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="fc769-155">**Recipient address**</span></span>
  - <span data-ttu-id="fc769-156">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="fc769-156">**Sender address**</span></span>
  - <span data-ttu-id="fc769-157">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="fc769-157">**Message ID**</span></span>
  - <span data-ttu-id="fc769-158">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-158">**File**</span></span>
  - <span data-ttu-id="fc769-159">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="fc769-159">**Subject**</span></span>

  <span data-ttu-id="fc769-160">Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="fc769-160">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fc769-161">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-162">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="fc769-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="fc769-163">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="fc769-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fc769-164">Rapport over afwezigheid voor Office 365-bericht</span><span class="sxs-lookup"><span data-stu-id="fc769-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fc769-165">In het rapport vrije voorkeuren voor **ATP-berichten** ziet u de acties die zijn ondernomen voor e-mailberichten die zijn gevonden met schadelijke inhoud.</span><span class="sxs-lookup"><span data-stu-id="fc769-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="fc769-166">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **Defender for Office 365 bericht dispositioning**.</span><span class="sxs-lookup"><span data-stu-id="fc769-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="fc769-167">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="fc769-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![De widget voor Office 365 voor het verplaatsen van berichten in het Dashboard rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fc769-169">De informatie in dit rapport is ook beschikbaar in het [rapport met bestandstypen van de Defender voor Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="fc769-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fc769-170">Rapportweergave voor het rapport over het wijzigen van de berichten voor de Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fc769-171">De volgende weergaven zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="fc769-171">The following views are available:</span></span>

- <span data-ttu-id="fc769-172">**Gegevens weergeven op: bericht** : de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-172">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fc769-173">**Toegang blokkeren**</span><span class="sxs-lookup"><span data-stu-id="fc769-173">**Block access**</span></span>
  - <span data-ttu-id="fc769-174">**Berichten vervangen**</span><span class="sxs-lookup"><span data-stu-id="fc769-174">**Messages replaced**</span></span>
  - <span data-ttu-id="fc769-175">**Berichten gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="fc769-175">**Messages monitored**</span></span>
  - <span data-ttu-id="fc769-176">**Vervangen door dynamische e-mail bezorging** : Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fc769-176">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fc769-178">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-178">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-179">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-180">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="fc769-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fc769-181">**Gegevens weergeven op: bestand** : de grafiek bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-181">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fc769-182">**Schadelijke Excel-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fc769-183">**Schadelijke Flash-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fc769-184">**Schadelijke PDF-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fc769-185">**Schadelijke PowerPoint-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fc769-186">**Schadelijke Url's**</span><span class="sxs-lookup"><span data-stu-id="fc769-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="fc769-187">**Schadelijke Word-bijlagen**</span><span class="sxs-lookup"><span data-stu-id="fc769-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fc769-188">**Schadelijke bijlagen met uitvoerbaar bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fc769-189">**Gezien**</span><span class="sxs-lookup"><span data-stu-id="fc769-189">**Others**</span></span>

  <span data-ttu-id="fc769-190">Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fc769-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fc769-192">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-192">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-193">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-194">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="fc769-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fc769-195">Weergave Details van het bericht voor het wijzigen van de weergave van het bericht voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fc769-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fc769-196">Als u klikt op **Details tabel weergeven** , biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen.</span><span class="sxs-lookup"><span data-stu-id="fc769-196">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fc769-197">Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="fc769-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fc769-198">**Gegevens weergeven op: bericht** :</span><span class="sxs-lookup"><span data-stu-id="fc769-198">**View data by: Message** :</span></span>

  - <span data-ttu-id="fc769-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fc769-199">**Date**</span></span>
  - <span data-ttu-id="fc769-200">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="fc769-200">**Recipient address**</span></span>
  - <span data-ttu-id="fc769-201">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="fc769-201">**Sender address**</span></span>
  - <span data-ttu-id="fc769-202">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="fc769-202">**Message ID**</span></span>
  - <span data-ttu-id="fc769-203">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-203">**File**</span></span>
  - <span data-ttu-id="fc769-204">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="fc769-204">**Subject**</span></span>

  <span data-ttu-id="fc769-205">Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="fc769-205">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fc769-206">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-207">Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.</span><span class="sxs-lookup"><span data-stu-id="fc769-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fc769-208">**Gegevens uit een bestand weergeven** :</span><span class="sxs-lookup"><span data-stu-id="fc769-208">**View data by: File** :</span></span>

  - <span data-ttu-id="fc769-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fc769-209">**Date**</span></span>
  - <span data-ttu-id="fc769-210">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="fc769-210">**Recipient address**</span></span>
  - <span data-ttu-id="fc769-211">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="fc769-211">**Sender address**</span></span>
  - <span data-ttu-id="fc769-212">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="fc769-212">**Message ID**</span></span>
  - <span data-ttu-id="fc769-213">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="fc769-213">**File**</span></span>

  <span data-ttu-id="fc769-214">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-214">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-215">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-216">De waarden van het bestandstype die zichtbaar zijn in de grafiek.</span><span class="sxs-lookup"><span data-stu-id="fc769-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="fc769-217">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="fc769-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="fc769-218">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="fc769-218">Threat protection status report</span></span>

<span data-ttu-id="fc769-219">Het rapport **status van bedreigingsbeveiliging** is één weergave waarin informatie wordt verzameld over schadelijke inhoud en ongewenste E-mail die wordt gedetecteerd en geblokkeerd via [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc769-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="fc769-220">Zie [statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fc769-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="fc769-221">Rapport over URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fc769-221">URL threat protection report</span></span>

<span data-ttu-id="fc769-222">Het **rapport URL Threat Protection** biedt samenvattings-en trend weergaven voor bedreigingen die worden gedetecteerd en acties die worden uitgevoerd op URL-klikken als onderdeel van [veilige koppelingen](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fc769-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="fc769-223">Dit rapport hoeft niet te klikken op gegevens van gebruikers waar voor het beleid voor veilige koppelingen de optie **gebruiker niet bijhouden** is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fc769-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="fc769-224">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport URL-beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="fc769-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="fc769-225">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="fc769-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![De widget URL-beveiligingsrapport in het Dashboard rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fc769-227">Dit is een *beveiligingsrapport* voor trends, wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="fc769-227">This is a *protection trend report* , meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="fc769-228">De gegevens in de samengevoegde weergave zijn daardoor niet in realtime beschikbaar, maar de gegevens in de tabel weergave Details is dus een lichte discrepantie tussen de twee weergaven.</span><span class="sxs-lookup"><span data-stu-id="fc769-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fc769-229">Rapportweergave voor het rapport URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fc769-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="fc769-230">Het rapport **URL Threat Protection** heeft twee geaggregeerde weergaven die elke vier uur worden vernieuwd met de gegevens voor de laatste 90 dagen:</span><span class="sxs-lookup"><span data-stu-id="fc769-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="fc769-231">**URL klik op beschermings actie** : toont het aantal gebruikers in de organisatie op basis van de URL en de resultaten van de Klik op:</span><span class="sxs-lookup"><span data-stu-id="fc769-231">**URL click protection action** : Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="fc769-232">**Geblokkeerd** (de gebruiker is geblokkeerd voor het navigeren naar de URL)</span><span class="sxs-lookup"><span data-stu-id="fc769-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="fc769-233">**Geblokkeerde en geklikt door**</span><span class="sxs-lookup"><span data-stu-id="fc769-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="fc769-234">**Door de scan geklikt**</span><span class="sxs-lookup"><span data-stu-id="fc769-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="fc769-235">Met een klik wordt aangegeven dat de gebruiker heeft geklikt op de blok pagina voor de schadelijke website (beheerders kunnen de klik-en-beleidsregels uitschakelen in beleidsregels voor veilige koppelingen).</span><span class="sxs-lookup"><span data-stu-id="fc769-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="fc769-236">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-236">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-237">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-238">De beschikbare klikken op beschermings acties plus de **toegestane** waarde (de gebruiker heeft de mogelijkheid om naar de URL te gaan).</span><span class="sxs-lookup"><span data-stu-id="fc769-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL klik op beschermings actie weergave in het rapport URL Threat Protection](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="fc769-240">**URL klik op toepassing** : hier ziet u het aantal te klikken voor de URL door toepassingen die ondersteuning bieden voor veilige koppelingen:</span><span class="sxs-lookup"><span data-stu-id="fc769-240">**URL click by application** : Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="fc769-241">**E-mailclient**</span><span class="sxs-lookup"><span data-stu-id="fc769-241">**Email client**</span></span>
  - <span data-ttu-id="fc769-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="fc769-242">**PowerPoint**</span></span>
  - <span data-ttu-id="fc769-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="fc769-243">**Word**</span></span>
  - <span data-ttu-id="fc769-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="fc769-244">**Excel**</span></span>
  - <span data-ttu-id="fc769-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="fc769-245">**OneNote**</span></span>
  - <span data-ttu-id="fc769-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="fc769-246">**Visio**</span></span>
  - <span data-ttu-id="fc769-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="fc769-247">**Teams**</span></span>
  - <span data-ttu-id="fc769-248">**Overige**</span><span class="sxs-lookup"><span data-stu-id="fc769-248">**Other**</span></span>

  <span data-ttu-id="fc769-249">Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="fc769-249">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fc769-250">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="fc769-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fc769-251">De beschikbare toepassingen.</span><span class="sxs-lookup"><span data-stu-id="fc769-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fc769-252">Weergave Details van het rapport URL Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fc769-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="fc769-253">Als u klikt op **Details tabel weergeven** , biedt het rapport een vrijwel realtime weergave van alle klikken die binnen de organisatie plaatsvinden voor de laatste 7 dagen, met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-253">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="fc769-254">**Klik op tijd**</span><span class="sxs-lookup"><span data-stu-id="fc769-254">**Click time**</span></span>
- <span data-ttu-id="fc769-255">**Gebruiker**</span><span class="sxs-lookup"><span data-stu-id="fc769-255">**User**</span></span>
- <span data-ttu-id="fc769-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="fc769-256">**URL**</span></span>
- <span data-ttu-id="fc769-257">**Actierij**</span><span class="sxs-lookup"><span data-stu-id="fc769-257">**Action**</span></span>
- <span data-ttu-id="fc769-258">**App**</span><span class="sxs-lookup"><span data-stu-id="fc769-258">**App**</span></span>

<span data-ttu-id="fc769-259">Als u in de weergave Details op **filters** klikt, kunt u filteren op dezelfde criteria als in de rapportweergave, en ook op **domeinen** of **geadresseerden** , gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="fc769-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="fc769-260">Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="fc769-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="fc769-261">Extra rapporten om weer te geven</span><span class="sxs-lookup"><span data-stu-id="fc769-261">Additional reports to view</span></span>

<span data-ttu-id="fc769-262">Naast de rapporten die in dit onderwerp worden beschreven, zijn er nog enkele andere rapporten beschikbaar, zoals beschreven in de volgende tabel:</span><span class="sxs-lookup"><span data-stu-id="fc769-262">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="fc769-263">Rapport</span><span class="sxs-lookup"><span data-stu-id="fc769-263">Report</span></span>|<span data-ttu-id="fc769-264">Rond</span><span class="sxs-lookup"><span data-stu-id="fc769-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="fc769-265">**Explorer** (Microsoft Defender voor Office 365 abonnement 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="fc769-265">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="fc769-266">Bedreigingsverkenner (en realtime detecties)</span><span class="sxs-lookup"><span data-stu-id="fc769-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="fc769-267">**Beveiligingsrapporten voor e-mail** , zoals het rapport belangrijkste afzenders en geadresseerden, het rapport spoofberichten en het rapport detectie van ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="fc769-267">**Email security reports** , such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="fc769-268">Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="fc769-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="fc769-269">**E-mail stroom rapporten** , zoals het doorsturen van rapporten, het rapport status van de mail stroom en het rapport meest voorkomende afzenders en geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="fc769-269">**Mail flow reports** , such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="fc769-270">De e-mail stroom rapporten weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="fc769-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="fc769-271">**URL-tracering voor veilige koppelingen** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fc769-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="fc769-272">De uitvoer van deze cmdlet toont u de resultaten van acties van veilige koppelingen in de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="fc769-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="fc769-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="fc769-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="fc769-274">**Resultaten van e-mail verkeer voor EOP en Microsoft Defender voor Office 365** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fc769-274">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="fc769-275">De uitvoer van deze cmdlet bevat informatie over domein, datum, evenement type, richting, actie en aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="fc769-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="fc769-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="fc769-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="fc769-277">**E-mail detailrapporten voor EOP en Defender voor Office 365 detectie** (alleen PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fc769-277">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="fc769-278">De uitvoer van deze cmdlet bevat details over schadelijke bestanden of Url's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.</span><span class="sxs-lookup"><span data-stu-id="fc769-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="fc769-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="fc769-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="fc769-280">Welke machtigingen zijn vereist voor het weergeven van de rapporten van de Defender for Office 365?</span><span class="sxs-lookup"><span data-stu-id="fc769-280">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="fc769-281">Voor het weergeven en gebruiken van de rapporten die in dit onderwerp worden beschreven, **moet u beschikken over de juiste rol die is toegewezen aan het beveiligings &amp; compliance en het Beheercentrum van Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fc769-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="fc769-282">Voor het beveiligings & nalevings centrum moet een van de volgende rollen zijn toegewezen:</span><span class="sxs-lookup"><span data-stu-id="fc769-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="fc769-283">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="fc769-283">Organization Management</span></span>
  - <span data-ttu-id="fc769-284">Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="fc769-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fc769-285">Beveiligings operator (dit kan worden toegewezen in het Azure Active Directory-beheercentrum [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="fc769-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fc769-286">Beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="fc769-286">Security Reader</span></span>

- <span data-ttu-id="fc769-287">Voor Exchange Online moet u beschikken over een van de volgende rollen die zijn toegewezen in het Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="fc769-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="fc769-288">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="fc769-288">Organization Management</span></span>
  - <span data-ttu-id="fc769-289">Organisatiebeheer alleen weergeven</span><span class="sxs-lookup"><span data-stu-id="fc769-289">View-only Organization Management</span></span>
  - <span data-ttu-id="fc769-290">Rollen View-Only geadresseerden</span><span class="sxs-lookup"><span data-stu-id="fc769-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="fc769-291">Nalevings beheer</span><span class="sxs-lookup"><span data-stu-id="fc769-291">Compliance Management</span></span>

<span data-ttu-id="fc769-292">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="fc769-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="fc769-293">Machtigingen in het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="fc769-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="fc769-294">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fc769-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="fc769-295">Wat moet ik doen als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="fc769-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="fc769-296">Als u geen gegevens ziet in uw 365-rapporten van Defender for Office, controleert u of uw beleidsregels correct zijn ingesteld.</span><span class="sxs-lookup"><span data-stu-id="fc769-296">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="fc769-297">Als u wilt dat de beveiliging van Defender voor Office 365 op de juiste plek is geconfigureerd, moet uw organisatie beleidsregels voor [veilige koppelingen](set-up-atp-safe-links-policies.md) en een beleid voor veilige [bijlagen](set-up-atp-safe-attachments-policies.md) definiëren.</span><span class="sxs-lookup"><span data-stu-id="fc769-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="fc769-298">Zie ook [antispam en bescherming tegen malware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fc769-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc769-299">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fc769-299">Related topics</span></span>

[<span data-ttu-id="fc769-300">Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="fc769-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="fc769-301">Rolmachtigingen (Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="fc769-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
