---
title: E-mail stroom rapporten weergeven in het Dashboard rapporten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie vinden over de e-mail stroom rapporten die beschikbaar zijn in het dashboard voor beveiliging & in het compliance-Beveiligingscentrum.
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578016"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="628f9-103">De e-mail stroom rapporten weergeven in het Dashboard rapporten in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="628f9-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="628f9-104">Naast de weergave van de e-mail stroom rapporten die beschikbaar zijn in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het beveiligings & nalevings centrum, zijn diverse extra e-mail flow rapporten beschikbaar in het Dashboard rapporten, zodat u uw microsoft 365-organisatie kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="628f9-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="628f9-105">Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)hebt, kunt u deze rapporten weergeven in het [compliance-beveiligings &](https://office.protection.com) door naar het **Reports** \> **Dashboard**rapporten te gaan.</span><span class="sxs-lookup"><span data-stu-id="628f9-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="628f9-106">Open om rechtstreeks naar het Dashboard rapporten te gaan <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="628f9-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="628f9-108">Verbindingslijn rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-108">Connector report</span></span>

<span data-ttu-id="628f9-109">In het **rapport connector** ziet u de activiteit van een e-mail stroom op de [binnenkomende en uitgaande connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="628f9-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="628f9-110">Als u het rapport wilt weergeven, opent u het [& nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **verbindingslijn rapport**.</span><span class="sxs-lookup"><span data-stu-id="628f9-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="628f9-111">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="628f9-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget rapport voor verbindingslijn in het Dashboard rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="628f9-113">Rapportweergave voor het verbindings rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-113">Report view for the Connector report</span></span>

<span data-ttu-id="628f9-114">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="628f9-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="628f9-115">**Gegevens weergeven op: e-mail stroom**: deze grafiek toont het aantal inkomende en uitgaande berichten, geordend op:</span><span class="sxs-lookup"><span data-stu-id="628f9-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="628f9-116">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="628f9-116">**Total**</span></span>
  - <span data-ttu-id="628f9-117">**Vanaf internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="628f9-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="628f9-118">**Naar Internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="628f9-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="628f9-119">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="628f9-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="628f9-120">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de optie **gegevens weergeven voor** besturingselement om een van deze opties of **alle e-mail stromen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="628f9-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens weergeven op e-mail stroom in het verbindings rapport](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="628f9-122">**Gegevens weergeven op: TLS**: dit diagram toont het percentage van de versie van de TLS (Transport Layer Security) voor de e-mail stroom.</span><span class="sxs-lookup"><span data-stu-id="628f9-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="628f9-123">U kunt de gegevens in de grafiek isoleren door de volgende opties te selecteren in het dialoog element **gegevens weergeven voor** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="628f9-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="628f9-124">**Alle e-mail stroom**</span><span class="sxs-lookup"><span data-stu-id="628f9-124">**All mail flow**</span></span>
  - <span data-ttu-id="628f9-125">**Vanaf internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="628f9-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="628f9-126">**Naar Internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="628f9-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="628f9-127">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="628f9-127">A specific connector that you've configured.</span></span>

  ![Gegevens per TLS-gebruik in het connector-rapport weergeven](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="628f9-129">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="628f9-130">De tabel weergave Details voor het verbindings rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-130">Details table view for the Connector report</span></span>

<span data-ttu-id="628f9-131">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="628f9-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="628f9-132">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-132">**Date**</span></span>
- <span data-ttu-id="628f9-133">**De richting en de naam van de verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="628f9-133">**Connector direction and name**</span></span>
- <span data-ttu-id="628f9-134">**Type verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="628f9-134">**Connector type**</span></span>
- <span data-ttu-id="628f9-135">**Afgedwongen TLS?**: de waarde **waar** of **Onwaar**.</span><span class="sxs-lookup"><span data-stu-id="628f9-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="628f9-136">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="628f9-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="628f9-137">**TLS 1,0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="628f9-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="628f9-138">**TLS 1,1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="628f9-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="628f9-139">**TLS 1,2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="628f9-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="628f9-140">**Volume**: het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="628f9-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="628f9-141">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="628f9-142">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="628f9-143">Rapport over Exchange-transportregels</span><span class="sxs-lookup"><span data-stu-id="628f9-143">Exchange transport rule report</span></span>

<span data-ttu-id="628f9-144">In het **rapport Exchange-transportregel** ziet u het effect van de regels voor de e-mail stroom (ook wel transport-regels genoemd) in inkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="628f9-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="628f9-145">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de optie **Exchange-Transport regel**.</span><span class="sxs-lookup"><span data-stu-id="628f9-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="628f9-146">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="628f9-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![De widget Exchange-transportregel in het Dashboard rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="628f9-148">Rapportweergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="628f9-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="628f9-149">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="628f9-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="628f9-150">**Gegevens weergeven op: Exchange-transportregels** \> **Opsplitsen op: richting**: deze grafiek toont het aantal **inkomende** en **uitgaande** berichten dat is beïnvloed door de transportregels.</span><span class="sxs-lookup"><span data-stu-id="628f9-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="628f9-151">**Gegevens weergeven op: Exchange-transportregels** \> **Verbreken op basis van: Ernst**: in dit diagram ziet u het aantal **hoge Ernst** en de ernst van de **Ernst**en van **lage Ernst** berichten.</span><span class="sxs-lookup"><span data-stu-id="628f9-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="628f9-152">U stelt het prioriteitsniveau als een actie in de regel in (**Controleer deze regel met een niveau hoger** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="628f9-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="628f9-153">Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="628f9-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="628f9-154">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Opsplitsen op: richting**: dit diagram toont het aantal **inkomende** en **uitgaande** berichten dat werd beïnvloed door DLP-transportregels (preventie van gegevensverlies).</span><span class="sxs-lookup"><span data-stu-id="628f9-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="628f9-155">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="628f9-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="628f9-156">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="628f9-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="628f9-157">**Gegevens weergeven voor: gekraakte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="628f9-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="628f9-158">**Gegevens weergeven voor: laag volume van de in de handel vastgestelde US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="628f9-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="628f9-159">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Onderbreek omlaag in: richting**: in deze weergave ziet u het aantal **hoge Ernst** en de **Ernst**en de **lage PRIORITEITs** berichten die zijn getroffen door DLP-transportregels.</span><span class="sxs-lookup"><span data-stu-id="628f9-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="628f9-160">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="628f9-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="628f9-161">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="628f9-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="628f9-162">**Gegevens weergeven voor: gekraakte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="628f9-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="628f9-163">**Gegevens weergeven voor: laag volume van de in de handel vastgestelde US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="628f9-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="628f9-164">Als u op **filters** in een rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters::</span><span class="sxs-lookup"><span data-stu-id="628f9-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="628f9-165">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="628f9-166">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="628f9-166">Direction values</span></span>
- <span data-ttu-id="628f9-167">Prioriteitswaarden</span><span class="sxs-lookup"><span data-stu-id="628f9-167">Severity values</span></span>

![Rapportweergave in het rapport Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="628f9-169">Detail tabel weergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="628f9-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="628f9-170">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="628f9-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="628f9-171">**Gegevens weergeven op: Exchange-Transport regels**:</span><span class="sxs-lookup"><span data-stu-id="628f9-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="628f9-172">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-172">**Date**</span></span>
  - <span data-ttu-id="628f9-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="628f9-173">**Transport rule**</span></span>
  - <span data-ttu-id="628f9-174">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="628f9-174">**Subject**</span></span>
  - <span data-ttu-id="628f9-175">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="628f9-175">**Sender address**</span></span>
  - <span data-ttu-id="628f9-176">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="628f9-176">**Recipient address**</span></span>
  - <span data-ttu-id="628f9-177">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="628f9-177">**Severity**</span></span>
  - <span data-ttu-id="628f9-178">**Richting**</span><span class="sxs-lookup"><span data-stu-id="628f9-178">**Direction**</span></span>

- <span data-ttu-id="628f9-179">**Gegevens weergeven op: DLP Exchange-transportregels**:</span><span class="sxs-lookup"><span data-stu-id="628f9-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="628f9-180">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-180">**Date**</span></span>
  - <span data-ttu-id="628f9-181">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="628f9-181">**DLP policy**</span></span>
  - <span data-ttu-id="628f9-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="628f9-182">**Transport rule**</span></span>
  - <span data-ttu-id="628f9-183">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="628f9-183">**Subject**</span></span>
  - <span data-ttu-id="628f9-184">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="628f9-184">**Sender address**</span></span>
  - <span data-ttu-id="628f9-185">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="628f9-185">**Recipient address**</span></span>
  - <span data-ttu-id="628f9-186">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="628f9-186">**Severity**</span></span>
  - <span data-ttu-id="628f9-187">**Richting**</span><span class="sxs-lookup"><span data-stu-id="628f9-187">**Direction**</span></span>

<span data-ttu-id="628f9-188">Als u in een weergave met detail tabellen op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="628f9-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="628f9-189">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="628f9-190">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="628f9-190">Direction values</span></span>
- <span data-ttu-id="628f9-191">Prioriteitswaarden</span><span class="sxs-lookup"><span data-stu-id="628f9-191">Severity values</span></span>

<span data-ttu-id="628f9-192">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="628f9-193">Doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-193">Forwarding report</span></span>

<span data-ttu-id="628f9-194">In het **doorstuur rapport** worden de automatisch doorgestuurde berichten van uw organisatie weergegeven naar externe domeinen vanuit postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="628f9-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="628f9-195">Doorgestuurde berichten kunnen zorgen voor beveiliging of compliance, en kunnen de inhoud van een gemanipuleerd account aangeven.</span><span class="sxs-lookup"><span data-stu-id="628f9-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="628f9-196">Als u het rapport wilt weergeven, opent u het [& nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **forwarding Report**.</span><span class="sxs-lookup"><span data-stu-id="628f9-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="628f9-197">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="628f9-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget rapport doorsturen in het Dashboard rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="628f9-199">Rapportweergave voor het doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="628f9-200">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="628f9-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="628f9-201">**Gegevens weergeven voor: doorstuur methoden**: de volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="628f9-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="628f9-202">**Transport regel**: ook wel wel [e-mail stroom regels](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)genoemd.</span><span class="sxs-lookup"><span data-stu-id="628f9-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="628f9-203">**Postvak regel**: ook wel bekend als de regels voor het [Postvak in](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="628f9-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Weergave doorstuur methoden in het doorstuur rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="628f9-205">**Gegevens weergeven voor: forwarding domains**: in deze weergave ziet u de domeinen van de ontvanger die de bestemmingen zijn voor doorsturen.</span><span class="sxs-lookup"><span data-stu-id="628f9-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Forwarding domains-weergave in het doorstuur rapport](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="628f9-207">**Gegevens weergeven voor: doorstuurservers**: de volgende doorstuurservers worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="628f9-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="628f9-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="628f9-208">**Transport rule**</span></span>
  - <span data-ttu-id="628f9-209">Het postvak met de regel voor Postvak in met doorstuurregels.</span><span class="sxs-lookup"><span data-stu-id="628f9-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Doorstuur weergaven in het doorstuur rapport](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="628f9-211">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="628f9-212">De tabel weergave Details voor het doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="628f9-213">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="628f9-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="628f9-214">**Doorstuurservers**: de Value **transport-regel** of het postvak met de regel voor Postvak in met de doorstuurregels.</span><span class="sxs-lookup"><span data-stu-id="628f9-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="628f9-215">**Forwarding type**: de **regel** voor het postvak of de **transport regel**.</span><span class="sxs-lookup"><span data-stu-id="628f9-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="628f9-216">**Naam van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="628f9-216">**Recipient name**</span></span>
- <span data-ttu-id="628f9-217">**Domein van de ontvanger**</span><span class="sxs-lookup"><span data-stu-id="628f9-217">**Recipient domain**</span></span>
- <span data-ttu-id="628f9-218">**Details**: dit is de GUID-waarde van de e-mail stroom regel of de RuleIdentity waarde van de regel voor Postvak in.</span><span class="sxs-lookup"><span data-stu-id="628f9-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="628f9-219">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-219">**Count**</span></span>
- <span data-ttu-id="628f9-220">**Eerste doorstuur datum**</span><span class="sxs-lookup"><span data-stu-id="628f9-220">**First forward date**</span></span>

<span data-ttu-id="628f9-221">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="628f9-222">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="628f9-223">Rapport over de status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="628f9-223">Mailflow status report</span></span>

<span data-ttu-id="628f9-224">Het rapport over de e-mail **stroom status** is vergelijkbaar met het [verzonden en ontvangen van e-mail](#sent-and-received-email-report), met aanvullende informatie over het toestaan of blokkeren van e-mailberichten op de rand.</span><span class="sxs-lookup"><span data-stu-id="628f9-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="628f9-225">Dit is het enige rapport met informatie over Edge-bescherming en geeft aan hoeveel e-mailberichten worden geblokkeerd voordat deze worden toegelaten door de service Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="628f9-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="628f9-226">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het rapport over de status van de **telestroom**.</span><span class="sxs-lookup"><span data-stu-id="628f9-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="628f9-227">Als u rechtstreeks naar het **rapport met de e-mail stroom status**wilt gaan, opent u het <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="628f9-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget statusrapport van de transstroom status in het Dashboard rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="628f9-229">Type weergave voor het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="628f9-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="628f9-230">Wanneer u het rapport opent, is het tabblad **type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="628f9-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="628f9-231">Deze weergave bevat standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="628f9-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="628f9-232">**Datum**: de laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="628f9-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="628f9-233">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="628f9-233">**Direction**:</span></span>

  - <span data-ttu-id="628f9-234">**Bound**</span><span class="sxs-lookup"><span data-stu-id="628f9-234">**Inbound**</span></span>
  - <span data-ttu-id="628f9-235">**Transfer**</span><span class="sxs-lookup"><span data-stu-id="628f9-235">**Outbound**</span></span>
  - <span data-ttu-id="628f9-236">**Intra organisatie** (geteld van de **inkomende** en **uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="628f9-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="628f9-237">**Type**:</span><span class="sxs-lookup"><span data-stu-id="628f9-237">**Type**:</span></span>

  - <span data-ttu-id="628f9-238">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-238">**Good mail**</span></span>
  - <span data-ttu-id="628f9-239">**Malware**</span><span class="sxs-lookup"><span data-stu-id="628f9-239">**Malware**</span></span>
  - <span data-ttu-id="628f9-240">**Spam**</span><span class="sxs-lookup"><span data-stu-id="628f9-240">**Spam**</span></span>
  - <span data-ttu-id="628f9-241">**Edge-bescherming**</span><span class="sxs-lookup"><span data-stu-id="628f9-241">**Edge protection**</span></span>
  - <span data-ttu-id="628f9-242">**Regel berichten**</span><span class="sxs-lookup"><span data-stu-id="628f9-242">**Rule messages**</span></span>
  - <span data-ttu-id="628f9-243">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-243">**Phishing email**</span></span>

<span data-ttu-id="628f9-244">De grafiek is ingedeeld op basis van de waarden in het **type** .</span><span class="sxs-lookup"><span data-stu-id="628f9-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="628f9-245">U kunt deze filters wijzigen door op **filter** te klikken of door op een waarde in de grafieklegenda te klikken.</span><span class="sxs-lookup"><span data-stu-id="628f9-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="628f9-246">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="628f9-246">The data table contains the following information:</span></span>

- <span data-ttu-id="628f9-247">**Richting**</span><span class="sxs-lookup"><span data-stu-id="628f9-247">**Direction**</span></span>
- <span data-ttu-id="628f9-248">**Type**</span><span class="sxs-lookup"><span data-stu-id="628f9-248">**Type**</span></span>
- <span data-ttu-id="628f9-249">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="628f9-249">**24 hours**</span></span>
- <span data-ttu-id="628f9-250">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="628f9-250">**3 days**</span></span>
- <span data-ttu-id="628f9-251">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="628f9-251">**7 days**</span></span>
- <span data-ttu-id="628f9-252">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="628f9-252">**15 days**</span></span>
- <span data-ttu-id="628f9-253">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="628f9-253">**30 days**</span></span>

<span data-ttu-id="628f9-254">Als u op **een categorie kiezen**klikt, kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="628f9-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="628f9-255">**Malafide e-mail**: met deze optie gaat u naar het rapport met de [bedreigings bescherming](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="628f9-256">**Malware in e-mail**: met deze optie gaat u naar het rapport met de [bedreigings bescherming](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="628f9-257">**Detectie van spam**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="628f9-258">**Geblokkeerde rand**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="628f9-259">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="628f9-259">**Export**:</span></span>

<span data-ttu-id="628f9-260">Voor de weergave Details kunt u alleen de gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="628f9-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="628f9-261">Als u gegevens voor zeven dagen wilt exporteren, moet u 7 verschillende export acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="628f9-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="628f9-262">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="628f9-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="628f9-263">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere. CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="628f9-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="628f9-264">Type weergave in het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="628f9-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="628f9-265">Richtings weergave voor het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="628f9-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="628f9-266">Als u op het tabblad **richting** klikt, worden de standaardfilters van de **type** weergave gebruikt.</span><span class="sxs-lookup"><span data-stu-id="628f9-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="628f9-267">De grafiek is ingedeeld op basis van **richtings** waarden.</span><span class="sxs-lookup"><span data-stu-id="628f9-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="628f9-268">U kunt deze filters wijzigen door te klikken op **filter** of door te klikken op een waarde in de legenda van de grafiek.</span><span class="sxs-lookup"><span data-stu-id="628f9-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="628f9-269">De filters van de **type** -weergave worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="628f9-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="628f9-270">De gegevenstabel bevat dezelfde informatie in de weergave **type** .</span><span class="sxs-lookup"><span data-stu-id="628f9-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="628f9-271">Het selectievakje **Kies een categorie voor meer details** , en de werking is hetzelfde als in de **type** weergave.</span><span class="sxs-lookup"><span data-stu-id="628f9-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="628f9-272">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="628f9-272">**Export**:</span></span>

<span data-ttu-id="628f9-273">Voor de weergave Details kunt u alleen de gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="628f9-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="628f9-274">Als u gegevens voor zeven dagen wilt exporteren, moet u 7 verschillende export acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="628f9-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="628f9-275">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="628f9-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="628f9-276">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere. CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="628f9-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="628f9-277">Richtings weergave in het rapport status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="628f9-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="628f9-278">E-mail verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="628f9-278">Sent and received email report</span></span>

<span data-ttu-id="628f9-279">Het rapport **verzonden en ontvangen e-mail** is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spam detectie, malware en e-mailberichten die als ' goed ' worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="628f9-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="628f9-280">In dit rapport worden de volgende gegevens weergegeven: [dit rapport bevat](#mailflow-status-report) geen gegevens over berichten die worden geblokkeerd door de Edge-bescherming.</span><span class="sxs-lookup"><span data-stu-id="628f9-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="628f9-281">De weergave statistisch en de weergave Details van het rapport zijn van 90 dagen filteren toegestaan.</span><span class="sxs-lookup"><span data-stu-id="628f9-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="628f9-282">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **e-mail verzonden en ontvangen**.</span><span class="sxs-lookup"><span data-stu-id="628f9-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="628f9-283">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="628f9-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget e-mail verzonden en ontvangen in het Dashboard rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="628f9-285">Rapportweergave voor het verzonden en ontvangen e-mail rapport</span><span class="sxs-lookup"><span data-stu-id="628f9-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="628f9-286">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="628f9-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="628f9-287">**Opsplitst op: type**: de grafiek bevat alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="628f9-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="628f9-288">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="628f9-288">**Total**</span></span>
  - <span data-ttu-id="628f9-289">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-289">**Good mail**</span></span>
  - <span data-ttu-id="628f9-290">**Malware (anti malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="628f9-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="628f9-291">**Detectie van spam**</span><span class="sxs-lookup"><span data-stu-id="628f9-291">**Spam detections**</span></span>
  - <span data-ttu-id="628f9-292">**Regel berichten**</span><span class="sxs-lookup"><span data-stu-id="628f9-292">**Rule messages**</span></span>
  - <span data-ttu-id="628f9-293">**Geavanceerde malware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="628f9-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="628f9-294">Wanneer u de muisaanwijzer op een dag (gegevenspunt) van de grafiek houdt, ziet u de gegevens voor die dag.</span><span class="sxs-lookup"><span data-stu-id="628f9-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Type weergave in het rapport verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="628f9-296">**Opsplitsen op: richting**: in de grafiek worden **totale**, **binnenkomende**en **uitgaande** gegevens weergegeven.</span><span class="sxs-lookup"><span data-stu-id="628f9-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="628f9-297">Wanneer u de muisaanwijzer op een dag (gegevenspunt) van de grafiek houdt, ziet u de gegevens voor die dag.</span><span class="sxs-lookup"><span data-stu-id="628f9-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![De weergaverichting in het rapport verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="628f9-299">**Inzoomen op** \> **Malware (anti malware)**: met deze optie gaat u naar de [detectie van malware in een e-mail rapport](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="628f9-300">**Inzoomen op** \> **Spam detectie)**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="628f9-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="628f9-301">Als u op **filters** in een rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="628f9-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="628f9-302">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="628f9-303">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="628f9-303">Direction values</span></span>
- <span data-ttu-id="628f9-304">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="628f9-304">Type values</span></span>

<span data-ttu-id="628f9-305">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="628f9-306">De tabel weergave Details voor het verzonden en ontvangen van een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="628f9-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="628f9-307">Als u klikt op **Details tabel weergeven** in de weergave van een oplopende **Volg** orde in: **richting** , wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="628f9-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="628f9-308">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="628f9-308">**Date (UTC)**</span></span>
- <span data-ttu-id="628f9-309">**Type**</span><span class="sxs-lookup"><span data-stu-id="628f9-309">**Type**</span></span>
- <span data-ttu-id="628f9-310">**Richting**</span><span class="sxs-lookup"><span data-stu-id="628f9-310">**Direction**</span></span>
- <span data-ttu-id="628f9-311">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="628f9-311">**Message count**</span></span>

<span data-ttu-id="628f9-312">Als u in een weergave met detail tabellen op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="628f9-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="628f9-313">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="628f9-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="628f9-314">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="628f9-314">Direction values</span></span>
- <span data-ttu-id="628f9-315">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="628f9-315">Type values</span></span>

<span data-ttu-id="628f9-316">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="628f9-317">Rapport belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="628f9-317">Top senders and recipients report</span></span>

<span data-ttu-id="628f9-318">De **meest voorkomende afzenders en geadresseerden** zijn een cirkeldiagram met uw belangrijkste afzenders en geadresseerden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="628f9-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="628f9-319">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **Reports** \> **Dashboard** rapporten en selecteert u **belangrijkste afzenders en geadresseerden**.</span><span class="sxs-lookup"><span data-stu-id="628f9-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="628f9-320">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="628f9-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Belangrijkste afzenders en widget geadresseerden in het Dashboard rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="628f9-322">Rapportweergave voor het rapport meest afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="628f9-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="628f9-323">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="628f9-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="628f9-324">**Gegevens voor de \> belangrijkste afzenders weergeven**</span><span class="sxs-lookup"><span data-stu-id="628f9-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="628f9-325">**Gegevens weergeven voor geadresseerden van de \> belangrijkste e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="628f9-326">**Gegevens voor de \> belangrijkste spam geadresseerden weergeven**</span><span class="sxs-lookup"><span data-stu-id="628f9-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="628f9-327">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="628f9-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="628f9-328">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="628f9-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="628f9-329">De compositie van het cirkeldiagram verandert op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="628f9-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="628f9-330">Wanneer u de muisaanwijzer boven een wig in het cirkeldiagram houdt, ziet u het aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="628f9-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="628f9-331">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="628f9-333">Weergave Details voor het rapport belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="628f9-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="628f9-334">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="628f9-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="628f9-335">**Gegevens voor de \> belangrijkste afzenders weergeven**</span><span class="sxs-lookup"><span data-stu-id="628f9-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="628f9-336">**Belangrijkste afzenders van e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-336">**Top mail senders**</span></span>
  - <span data-ttu-id="628f9-337">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-337">**Count**</span></span>

- <span data-ttu-id="628f9-338">**Gegevens weergeven voor geadresseerden van de \> belangrijkste e-mail**</span><span class="sxs-lookup"><span data-stu-id="628f9-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="628f9-339">**Belangrijkste e-mail geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="628f9-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="628f9-340">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-340">**Count**</span></span>

- <span data-ttu-id="628f9-341">**Gegevens voor de \> belangrijkste spam geadresseerden weergeven**</span><span class="sxs-lookup"><span data-stu-id="628f9-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="628f9-342">**Belangrijkste spam geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="628f9-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="628f9-343">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-343">**Count**</span></span>

- <span data-ttu-id="628f9-344">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="628f9-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="628f9-345">**Belangrijkste geadresseerden voor malware**</span><span class="sxs-lookup"><span data-stu-id="628f9-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="628f9-346">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-346">**Count**</span></span>

- <span data-ttu-id="628f9-347">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="628f9-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="628f9-348">**Belangrijkste geadresseerden voor malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="628f9-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="628f9-349">**Getal**</span><span class="sxs-lookup"><span data-stu-id="628f9-349">**Count**</span></span>

<span data-ttu-id="628f9-350">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="628f9-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="628f9-351">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="628f9-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="628f9-352">Welke machtigingen zijn vereist voor het weergeven van deze rapporten?</span><span class="sxs-lookup"><span data-stu-id="628f9-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="628f9-353">Als u de rapporten wilt weergeven en gebruiken, moet u lid zijn van de opgegeven rollen groep in het beveiligings & nalevings centrum **en** in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="628f9-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="628f9-354">In het nalevings centrum beveiligings & moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="628f9-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="628f9-355">-Organisatiebeheer-beveiligingsbeheerder (u kunt dit ook doen in het [Azure Active Directory-beheercentrum](https://aad.portal.azure.com) -beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="628f9-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="628f9-356">Zie [Machtigingen in het Beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="628f9-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="628f9-357">In Exchange Online moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="628f9-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="628f9-358">-Organisatiebeheer-alleen-bekijken Organisatiebeheer-alleen voor weergeven geadresseerden</span><span class="sxs-lookup"><span data-stu-id="628f9-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="628f9-359">Zie [machtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) en [rollen groepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="628f9-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="628f9-360">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="628f9-360">Related topics</span></span>

[<span data-ttu-id="628f9-361">Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="628f9-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="628f9-362">E-mail stroom inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="628f9-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="628f9-363">Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="628f9-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="628f9-364">Rapporten weergeven voor Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="628f9-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
