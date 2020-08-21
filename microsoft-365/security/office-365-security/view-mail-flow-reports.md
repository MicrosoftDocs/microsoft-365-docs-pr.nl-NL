---
title: E-mail stroom rapporten weergeven in het Dashboard rapporten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 9e9249eab5d3519dac0e33acf40d600d471b7cb2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826455"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="5ee88-103">De e-mail stroom rapporten weergeven in het Dashboard rapporten in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="5ee88-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="5ee88-104">Naast de weergave van de e-mail stroom rapporten die beschikbaar zijn in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het beveiligings & nalevings centrum, zijn diverse extra e-mail flow rapporten beschikbaar in het Dashboard rapporten, zodat u uw microsoft 365-organisatie kunt volgen.</span><span class="sxs-lookup"><span data-stu-id="5ee88-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="5ee88-105">Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)hebt, kunt u deze rapporten weergeven in het [compliance-beveiligings &](https://office.protection.com) door naar het **Reports** \> **Dashboard**rapporten te gaan.</span><span class="sxs-lookup"><span data-stu-id="5ee88-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="5ee88-106">Open om rechtstreeks naar het Dashboard rapporten te gaan <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="5ee88-108">Verbindingslijn rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-108">Connector report</span></span>

<span data-ttu-id="5ee88-109">In het **rapport connector** ziet u de activiteit van een e-mail stroom op de [binnenkomende en uitgaande connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="5ee88-110">Als u het rapport wilt weergeven, opent u het [& nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **verbindingslijn rapport**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="5ee88-111">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget rapport voor verbindingslijn in het Dashboard rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="5ee88-113">Rapportweergave voor het verbindings rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-113">Report view for the Connector report</span></span>

<span data-ttu-id="5ee88-114">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="5ee88-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="5ee88-115">**Gegevens weergeven op: e-mail stroom**: deze grafiek toont het aantal inkomende en uitgaande berichten, geordend op:</span><span class="sxs-lookup"><span data-stu-id="5ee88-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="5ee88-116">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-116">**Total**</span></span>
  - <span data-ttu-id="5ee88-117">**Vanaf internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="5ee88-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="5ee88-118">**Naar Internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="5ee88-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="5ee88-119">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="5ee88-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="5ee88-120">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de optie **gegevens weergeven voor** besturingselement om een van deze opties of **alle e-mail stromen**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens weergeven op e-mail stroom in het verbindings rapport](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="5ee88-122">**Gegevens weergeven op: TLS**: dit diagram toont het percentage van de versie van de TLS (Transport Layer Security) voor de e-mail stroom.</span><span class="sxs-lookup"><span data-stu-id="5ee88-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="5ee88-123">U kunt de gegevens in de grafiek isoleren door de volgende opties te selecteren in het dialoog element **gegevens weergeven voor** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="5ee88-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="5ee88-124">**Alle e-mail stroom**</span><span class="sxs-lookup"><span data-stu-id="5ee88-124">**All mail flow**</span></span>
  - <span data-ttu-id="5ee88-125">**Vanaf internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="5ee88-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="5ee88-126">**Naar Internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="5ee88-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="5ee88-127">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="5ee88-127">A specific connector that you've configured.</span></span>

  ![Gegevens per TLS-gebruik in het connector-rapport weergeven](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="5ee88-129">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="5ee88-130">De tabel weergave Details voor het verbindings rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-130">Details table view for the Connector report</span></span>

<span data-ttu-id="5ee88-131">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5ee88-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5ee88-132">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-132">**Date**</span></span>
- <span data-ttu-id="5ee88-133">**De richting en de naam van de verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="5ee88-133">**Connector direction and name**</span></span>
- <span data-ttu-id="5ee88-134">**Type verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="5ee88-134">**Connector type**</span></span>
- <span data-ttu-id="5ee88-135">**Afgedwongen TLS?**: de waarde **waar** of **Onwaar**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="5ee88-136">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="5ee88-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="5ee88-137">**TLS 1,0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="5ee88-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="5ee88-138">**TLS 1,1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="5ee88-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="5ee88-139">**TLS 1,2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="5ee88-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="5ee88-140">**Volume**: het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="5ee88-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="5ee88-141">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5ee88-142">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="5ee88-143">Rapport over Exchange-transportregels</span><span class="sxs-lookup"><span data-stu-id="5ee88-143">Exchange transport rule report</span></span>

<span data-ttu-id="5ee88-144">In het **rapport Exchange-transportregel** ziet u het effect van de regels voor de e-mail stroom (ook wel transport-regels genoemd) in inkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="5ee88-145">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de optie **Exchange-Transport regel**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="5ee88-146">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![De widget Exchange-transportregel in het Dashboard rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="5ee88-148">Rapportweergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="5ee88-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="5ee88-149">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="5ee88-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="5ee88-150">**Gegevens weergeven op: Exchange-transportregels** \> **Opsplitsen op: richting**: deze grafiek toont het aantal **inkomende** en **uitgaande** berichten dat is beïnvloed door de transportregels.</span><span class="sxs-lookup"><span data-stu-id="5ee88-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="5ee88-151">**Gegevens weergeven op: Exchange-transportregels** \> **Verbreken op basis van: Ernst**: in dit diagram ziet u het aantal **hoge Ernst** en de ernst van de **Ernst**en van **lage Ernst** berichten.</span><span class="sxs-lookup"><span data-stu-id="5ee88-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="5ee88-152">U stelt het prioriteitsniveau als een actie in de regel in (**Controleer deze regel met een niveau hoger** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="5ee88-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="5ee88-153">Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="5ee88-154">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Opsplitsen op: richting**: dit diagram toont het aantal **inkomende** en **uitgaande** berichten dat werd beïnvloed door DLP-transportregels (preventie van gegevensverlies).</span><span class="sxs-lookup"><span data-stu-id="5ee88-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="5ee88-155">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="5ee88-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="5ee88-156">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="5ee88-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="5ee88-157">**Gegevens weergeven voor: gekraakte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="5ee88-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="5ee88-158">**Gegevens weergeven voor: laag volume van de in de handel vastgestelde US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="5ee88-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="5ee88-159">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Onderbreek omlaag in: richting**: in deze weergave ziet u het aantal **hoge Ernst** en de **Ernst**en de **lage PRIORITEITs** berichten die zijn getroffen door DLP-transportregels.</span><span class="sxs-lookup"><span data-stu-id="5ee88-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="5ee88-160">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="5ee88-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="5ee88-161">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="5ee88-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="5ee88-162">**Gegevens weergeven voor: gekraakte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="5ee88-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="5ee88-163">**Gegevens weergeven voor: laag volume van de in de handel vastgestelde US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="5ee88-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="5ee88-164">Als u op **filters** in een rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters::</span><span class="sxs-lookup"><span data-stu-id="5ee88-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="5ee88-165">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="5ee88-166">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-166">Direction values</span></span>
- <span data-ttu-id="5ee88-167">Prioriteitswaarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-167">Severity values</span></span>

![Rapportweergave in het rapport Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="5ee88-169">Detail tabel weergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="5ee88-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="5ee88-170">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="5ee88-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5ee88-171">**Gegevens weergeven op: Exchange-Transport regels**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="5ee88-172">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-172">**Date**</span></span>
  - <span data-ttu-id="5ee88-173">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="5ee88-173">**Transport rule**</span></span>
  - <span data-ttu-id="5ee88-174">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="5ee88-174">**Subject**</span></span>
  - <span data-ttu-id="5ee88-175">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="5ee88-175">**Sender address**</span></span>
  - <span data-ttu-id="5ee88-176">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="5ee88-176">**Recipient address**</span></span>
  - <span data-ttu-id="5ee88-177">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="5ee88-177">**Severity**</span></span>
  - <span data-ttu-id="5ee88-178">**Richting**</span><span class="sxs-lookup"><span data-stu-id="5ee88-178">**Direction**</span></span>

- <span data-ttu-id="5ee88-179">**Gegevens weergeven op: DLP Exchange-transportregels**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="5ee88-180">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-180">**Date**</span></span>
  - <span data-ttu-id="5ee88-181">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="5ee88-181">**DLP policy**</span></span>
  - <span data-ttu-id="5ee88-182">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="5ee88-182">**Transport rule**</span></span>
  - <span data-ttu-id="5ee88-183">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="5ee88-183">**Subject**</span></span>
  - <span data-ttu-id="5ee88-184">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="5ee88-184">**Sender address**</span></span>
  - <span data-ttu-id="5ee88-185">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="5ee88-185">**Recipient address**</span></span>
  - <span data-ttu-id="5ee88-186">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="5ee88-186">**Severity**</span></span>
  - <span data-ttu-id="5ee88-187">**Richting**</span><span class="sxs-lookup"><span data-stu-id="5ee88-187">**Direction**</span></span>

<span data-ttu-id="5ee88-188">Als u in een weergave met detail tabellen op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="5ee88-189">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="5ee88-190">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-190">Direction values</span></span>
- <span data-ttu-id="5ee88-191">Prioriteitswaarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-191">Severity values</span></span>

<span data-ttu-id="5ee88-192">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="5ee88-193">Doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-193">Forwarding report</span></span>

<span data-ttu-id="5ee88-194">In het **doorstuur rapport** worden de automatisch doorgestuurde berichten van uw organisatie weergegeven naar externe domeinen vanuit postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ee88-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="5ee88-195">Doorgestuurde berichten kunnen zorgen voor beveiliging of compliance, en kunnen de inhoud van een gemanipuleerd account aangeven.</span><span class="sxs-lookup"><span data-stu-id="5ee88-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="5ee88-196">Als u het rapport wilt weergeven, opent u het [& nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **forwarding Report**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="5ee88-197">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget rapport doorsturen in het Dashboard rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="5ee88-199">Rapportweergave voor het doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="5ee88-200">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="5ee88-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="5ee88-201">**Gegevens weergeven voor: doorstuur methoden**: de volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5ee88-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="5ee88-202">**Transport regel**: ook wel wel [e-mail stroom regels](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)genoemd.</span><span class="sxs-lookup"><span data-stu-id="5ee88-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="5ee88-203">**Postvak regel**: ook wel bekend als de regels voor het [Postvak in](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="5ee88-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Weergave doorstuur methoden in het doorstuur rapport](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="5ee88-205">**Gegevens weergeven voor: forwarding domains**: in deze weergave ziet u de domeinen van de ontvanger die de bestemmingen zijn voor doorsturen.</span><span class="sxs-lookup"><span data-stu-id="5ee88-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Forwarding domains-weergave in het doorstuur rapport](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="5ee88-207">**Gegevens weergeven voor: doorstuurservers**: de volgende doorstuurservers worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5ee88-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="5ee88-208">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="5ee88-208">**Transport rule**</span></span>
  - <span data-ttu-id="5ee88-209">Het postvak met de regel voor Postvak in met doorstuurregels.</span><span class="sxs-lookup"><span data-stu-id="5ee88-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Doorstuur weergaven in het doorstuur rapport](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="5ee88-211">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="5ee88-212">De tabel weergave Details voor het doorstuur rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="5ee88-213">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5ee88-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5ee88-214">**Doorstuurservers**: de Value **transport-regel** of het postvak met de regel voor Postvak in met de doorstuurregels.</span><span class="sxs-lookup"><span data-stu-id="5ee88-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="5ee88-215">**Forwarding type**: de **regel** voor het postvak of de **transport regel**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="5ee88-216">**Naam van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="5ee88-216">**Recipient name**</span></span>
- <span data-ttu-id="5ee88-217">**Domein van de ontvanger**</span><span class="sxs-lookup"><span data-stu-id="5ee88-217">**Recipient domain**</span></span>
- <span data-ttu-id="5ee88-218">**Details**: dit is de GUID-waarde van de e-mail stroom regel of de RuleIdentity waarde van de regel voor Postvak in.</span><span class="sxs-lookup"><span data-stu-id="5ee88-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="5ee88-219">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-219">**Count**</span></span>
- <span data-ttu-id="5ee88-220">**Eerste doorstuur datum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-220">**First forward date**</span></span>

<span data-ttu-id="5ee88-221">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5ee88-222">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="5ee88-223">Rapport over de status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="5ee88-223">Mailflow status report</span></span>

<span data-ttu-id="5ee88-224">Het rapport over de e-mail **stroom status** is vergelijkbaar met het [verzonden en ontvangen van e-mail](#sent-and-received-email-report), met aanvullende informatie over het toestaan of blokkeren van e-mailberichten op de rand.</span><span class="sxs-lookup"><span data-stu-id="5ee88-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="5ee88-225">Dit is het enige rapport met informatie over Edge-bescherming en geeft aan hoeveel e-mailberichten worden geblokkeerd voordat deze worden toegelaten door de service Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5ee88-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="5ee88-226">Het is belangrijk om te weten dat wanneer een bericht wordt verzonden naar vijf geadresseerden, de waarde wordt geteld als vijf verschillende berichten en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="5ee88-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="5ee88-227">Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het rapport over de status van de **telestroom**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="5ee88-228">Als u rechtstreeks naar het **rapport met de e-mail stroom status**wilt gaan, opent u het <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget statusrapport van de transstroom status in het Dashboard rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="5ee88-230">Type weergave voor het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="5ee88-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="5ee88-231">Wanneer u het rapport opent, is het tabblad **type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="5ee88-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="5ee88-232">Deze weergave bevat standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="5ee88-233">**Datum**: de laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="5ee88-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="5ee88-234">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-234">**Direction**:</span></span>

  - <span data-ttu-id="5ee88-235">**Bound**</span><span class="sxs-lookup"><span data-stu-id="5ee88-235">**Inbound**</span></span>
  - <span data-ttu-id="5ee88-236">**Transfer**</span><span class="sxs-lookup"><span data-stu-id="5ee88-236">**Outbound**</span></span>
  - <span data-ttu-id="5ee88-237">**Intra organisatie**: dit aantal is bedoeld voor berichten in een Tenant, d.w.z.</span><span class="sxs-lookup"><span data-stu-id="5ee88-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5ee88-238">Sender abc@domain.com verzendt naar de xyz@domain.com van de geadresseerde (geteld op een afzonderlijke waarde van **Inkomend** en **uitgaand**)</span><span class="sxs-lookup"><span data-stu-id="5ee88-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="5ee88-239">**Type**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-239">**Type**:</span></span>

  - <span data-ttu-id="5ee88-240">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-240">**Good mail**</span></span>
  - <span data-ttu-id="5ee88-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="5ee88-241">**Malware**</span></span>
  - <span data-ttu-id="5ee88-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="5ee88-242">**Spam**</span></span>
  - <span data-ttu-id="5ee88-243">**Edge-bescherming**</span><span class="sxs-lookup"><span data-stu-id="5ee88-243">**Edge protection**</span></span>
  - <span data-ttu-id="5ee88-244">**Regel berichten**</span><span class="sxs-lookup"><span data-stu-id="5ee88-244">**Rule messages**</span></span>
  - <span data-ttu-id="5ee88-245">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-245">**Phishing email**</span></span>

<span data-ttu-id="5ee88-246">De grafiek is ingedeeld op basis van de waarden in het **type** .</span><span class="sxs-lookup"><span data-stu-id="5ee88-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="5ee88-247">U kunt deze filters wijzigen door te klikken op **filter** of door te klikken op een waarde in de legenda van de grafiek.</span><span class="sxs-lookup"><span data-stu-id="5ee88-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="5ee88-248">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="5ee88-248">The data table contains the following information:</span></span>

- <span data-ttu-id="5ee88-249">**Richting**</span><span class="sxs-lookup"><span data-stu-id="5ee88-249">**Direction**</span></span>
- <span data-ttu-id="5ee88-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="5ee88-250">**Type**</span></span>
- <span data-ttu-id="5ee88-251">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="5ee88-251">**24 hours**</span></span>
- <span data-ttu-id="5ee88-252">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="5ee88-252">**3 days**</span></span>
- <span data-ttu-id="5ee88-253">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="5ee88-253">**7 days**</span></span>
- <span data-ttu-id="5ee88-254">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="5ee88-254">**15 days**</span></span>
- <span data-ttu-id="5ee88-255">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="5ee88-255">**30 days**</span></span>

<span data-ttu-id="5ee88-256">Als u op **een categorie kiezen**klikt, kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="5ee88-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="5ee88-257">**Malafide e-mail**: met deze optie gaat u naar het rapport met de [bedreigings bescherming](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5ee88-258">**Malware in e-mail**: met deze optie gaat u naar het rapport met de [bedreigings bescherming](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5ee88-259">**Detectie van spam**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="5ee88-260">**Geblokkeerde rand**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="5ee88-261">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-261">**Export**:</span></span>

<span data-ttu-id="5ee88-262">Voor de weergave Details kunt u alleen de gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5ee88-263">Als u gegevens voor zeven dagen wilt exporteren, moet u 7 verschillende export acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5ee88-264">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="5ee88-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5ee88-265">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere. CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="5ee88-266">Type weergave in het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="5ee88-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="5ee88-267">Richtings weergave voor het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="5ee88-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="5ee88-268">Als u op het tabblad **richting** klikt, worden de standaardfilters van de **type** weergave gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="5ee88-269">De grafiek is ingedeeld op basis van **richtings** waarden.</span><span class="sxs-lookup"><span data-stu-id="5ee88-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="5ee88-270">U kunt deze filters wijzigen door te klikken op **filter** of door te klikken op een waarde in de legenda van de grafiek.</span><span class="sxs-lookup"><span data-stu-id="5ee88-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="5ee88-271">De filters van de **type** -weergave worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5ee88-272">De gegevenstabel bevat dezelfde informatie in de weergave **type** .</span><span class="sxs-lookup"><span data-stu-id="5ee88-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="5ee88-273">Het selectievakje **Kies een categorie voor meer details** , en de werking is hetzelfde als in de **type** weergave.</span><span class="sxs-lookup"><span data-stu-id="5ee88-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="5ee88-274">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-274">**Export**:</span></span>

<span data-ttu-id="5ee88-275">Voor de weergave Details kunt u alleen de gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5ee88-276">Als u gegevens voor zeven dagen wilt exporteren, moet u 7 verschillende export acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5ee88-277">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="5ee88-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5ee88-278">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere. CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="5ee88-279">Richtings weergave in het rapport status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="5ee88-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="5ee88-280">Trechter weergave voor het rapport status van de mailflow</span><span class="sxs-lookup"><span data-stu-id="5ee88-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="5ee88-281">In de weergave **trechter** ziet u hoe de functies voor e-mail risico beveiliging van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="5ee88-282">Dit bevat details over het totale aantal e-mails en hoe de geconfigureerde functies van bedreigingen voor beveiliging, waaronder Edge-beveiliging, anti-spam, anti-spam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="5ee88-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="5ee88-283">Als u op het tabblad **trechter** klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="5ee88-284">**Datum**: de laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="5ee88-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5ee88-285">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-285">**Direction**:</span></span>

  - <span data-ttu-id="5ee88-286">**Bound**</span><span class="sxs-lookup"><span data-stu-id="5ee88-286">**Inbound**</span></span>
  - <span data-ttu-id="5ee88-287">**Transfer**</span><span class="sxs-lookup"><span data-stu-id="5ee88-287">**Outbound**</span></span>
  - <span data-ttu-id="5ee88-288">**Intra organisatie**: dit aantal is bestemd voor berichten die binnen een Tenant worden verzonden; verzender abc@domain.com verzendt naar de xyz@domain.com van de geadresseerde (geteld van de inkomende en uitgaande waarde).</span><span class="sxs-lookup"><span data-stu-id="5ee88-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="5ee88-289">De weergave geaggregeerde weergave en gegevenstabel bieden ondersteuning voor 90 dagen van filteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5ee88-290">Als u op **filter**klikt, kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="5ee88-291">In dit diagram ziet u het aantal e-mailberichten ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="5ee88-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="5ee88-292">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-292">**Total email**</span></span>
- <span data-ttu-id="5ee88-293">**E-mail na bescherming van de Edge**</span><span class="sxs-lookup"><span data-stu-id="5ee88-293">**Email after edge protection**</span></span>
- <span data-ttu-id="5ee88-294">**E-mail na anti-malware, bestands reputatie, bestandstype blok**</span><span class="sxs-lookup"><span data-stu-id="5ee88-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="5ee88-295">**E-mail na anti-spam, URL-reputatie, merkloze persoon, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="5ee88-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="5ee88-296">**E-mail na anti-spam, filteren van bulk e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="5ee88-297">**E-mail nadat gebruikers-en domein imitatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5ee88-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="5ee88-298">**E-mail na bestand en URL-detonatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5ee88-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="5ee88-299">**E-mail waarvan de bescherming na de bezorging is verdacht**</span><span class="sxs-lookup"><span data-stu-id="5ee88-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="5ee88-300"><sup>1</sup> Office 365 alleen ATP</span><span class="sxs-lookup"><span data-stu-id="5ee88-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="5ee88-301">Als u het e-mailbericht dat u hebt gefilterd op EOP of ATP afzonderlijk wilt bekijken, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="5ee88-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="5ee88-302">De gegevenstabel bevat de volgende informatie, weergegeven in aflopende volgorde van datum:</span><span class="sxs-lookup"><span data-stu-id="5ee88-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5ee88-303">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-303">**Date**</span></span>
- <span data-ttu-id="5ee88-304">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-304">**Total email**</span></span>
- <span data-ttu-id="5ee88-305">**Edge-bescherming**</span><span class="sxs-lookup"><span data-stu-id="5ee88-305">**Edge protection**</span></span>
- <span data-ttu-id="5ee88-306">**Anti malware, bestands reputatie, bestandstype blok**</span><span class="sxs-lookup"><span data-stu-id="5ee88-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="5ee88-307">**Anti-phishing, URL-reputatie, merk imitatie, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="5ee88-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="5ee88-308">**Anti spam, filteren van bulk e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="5ee88-309">**Dispersonatie van gebruikers en domeinen (ATP)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="5ee88-310">**Bestand en URL-detonatie (ATP)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="5ee88-311">**Beveiligingsupdate voor de na ontvangst en ZAP (ATP) of ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="5ee88-312">Als u een rij in de gegevenstabel selecteert, worden in het vervolgmenu een extra uitsplitsing van het aantal e-mailberichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5ee88-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="5ee88-313">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-313">**Export**:</span></span>

<span data-ttu-id="5ee88-314">Nadat u op **exporteren** hebt **geklikt, kunt**u een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="5ee88-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="5ee88-315">**Samenvatting (met de gegevens voor de laatste 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5ee88-316">**Details (met gegevens voor de laatste 30 dagen op de meeste)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5ee88-317">Kies een bereik onder **datum**en klik vervolgens op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5ee88-318">De gegevens voor de huidige filters worden geëxporteerd naar een. CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="5ee88-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5ee88-319">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="5ee88-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5ee88-320">Als de gegevens meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="5ee88-321">Trechter weergave in het rapport status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="5ee88-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="5ee88-322">Technische weergave voor het rapport status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="5ee88-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="5ee88-323">De **technische weergave** is vergelijkbaar met de **trechter** weergave, met meer gedetailleerde informatie over de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="5ee88-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="5ee88-324">U kunt in de grafiek zien hoe berichten zijn gecategoriseerd in de verschillende stadia van bedreigings bescherming.</span><span class="sxs-lookup"><span data-stu-id="5ee88-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="5ee88-325">Als u op het tabblad **tech View** klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="5ee88-326">**Datum**: de laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="5ee88-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5ee88-327">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-327">**Direction**:</span></span>

  - <span data-ttu-id="5ee88-328">**Bound**</span><span class="sxs-lookup"><span data-stu-id="5ee88-328">**Inbound**</span></span>
  - <span data-ttu-id="5ee88-329">**Transfer**</span><span class="sxs-lookup"><span data-stu-id="5ee88-329">**Outbound**</span></span>
  - <span data-ttu-id="5ee88-330">**Intra organisatie**: dit aantal is bedoeld voor berichten in een Tenant, d.w.z.</span><span class="sxs-lookup"><span data-stu-id="5ee88-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5ee88-331">Sender abc@domain.com verzendt naar de xyz@domain.com van de geadresseerde (geteld op een afzonderlijke waarde van inkomend en uitgaand)</span><span class="sxs-lookup"><span data-stu-id="5ee88-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="5ee88-332">De weergave geaggregeerde weergave en gegevenstabel bieden ondersteuning voor 90 dagen van filteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5ee88-333">Als u op **filter**klikt, kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="5ee88-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="5ee88-334">In dit diagram ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="5ee88-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="5ee88-335">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-335">**Total email**</span></span>
- <span data-ttu-id="5ee88-336">**Rand toegestaan, gefilterd rand**</span><span class="sxs-lookup"><span data-stu-id="5ee88-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="5ee88-337">**Geen malware, detectie van detectie van schadelijke bijlagen, detectie van malware van malware, regelblok**</span><span class="sxs-lookup"><span data-stu-id="5ee88-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="5ee88-338">**Niet phishing, DMARC mislukking, imitatie detectie, phishing detectie, phishing detection**</span><span class="sxs-lookup"><span data-stu-id="5ee88-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="5ee88-339">**Geen detectie met URL-detonatie, URL-detonatie detectie (ATP)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="5ee88-340">**Geen spam, spam**</span><span class="sxs-lookup"><span data-stu-id="5ee88-340">**Not spam, spam**</span></span>
- <span data-ttu-id="5ee88-341">**Niet-kwaadaardige e-mail, detectie van veilige koppelingen (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="5ee88-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="5ee88-342">Wanneer u de muisaanwijzer op een categorie in de grafiek houdt, ziet u het aantal berichten in die categorie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="5ee88-343">De gegevenstabel bevat de volgende informatie, weergegeven in aflopende volgorde van datum:</span><span class="sxs-lookup"><span data-stu-id="5ee88-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5ee88-344">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-344">**Date**</span></span>
- <span data-ttu-id="5ee88-345">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-345">**Total email**</span></span>
- <span data-ttu-id="5ee88-346">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="5ee88-346">**Edge filtered**</span></span>
- <span data-ttu-id="5ee88-347">**Anti malware-engine, veilige bijlagen, gefilterde regel**</span><span class="sxs-lookup"><span data-stu-id="5ee88-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="5ee88-348">**DMARC, imitatie, spoofing, phishing gefilterd**</span><span class="sxs-lookup"><span data-stu-id="5ee88-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="5ee88-349">**Detectie van URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="5ee88-349">**URL detonation detection**</span></span>
- <span data-ttu-id="5ee88-350">**Anti spam gefilterd**</span><span class="sxs-lookup"><span data-stu-id="5ee88-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="5ee88-351">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="5ee88-351">**ZAP removed**</span></span>
- <span data-ttu-id="5ee88-352">**Detectie via veilige koppelingen**</span><span class="sxs-lookup"><span data-stu-id="5ee88-352">**Detection by safe links**</span></span>

<span data-ttu-id="5ee88-353">Als u een rij in de gegevenstabel selecteert, worden in het vervolgmenu een extra uitsplitsing van het aantal e-mailberichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5ee88-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="5ee88-354">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="5ee88-354">**Export**:</span></span>

<span data-ttu-id="5ee88-355">Bij klikken op **exporteren**kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="5ee88-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="5ee88-356">**Samenvatting (met de gegevens voor de laatste 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5ee88-357">**Details (met gegevens voor de laatste 30 dagen op de meeste)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5ee88-358">Kies een bereik onder **datum**en klik vervolgens op **toepassen**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5ee88-359">De gegevens voor de huidige filters worden geëxporteerd naar een. CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="5ee88-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5ee88-360">Elk geëxporteerde CSV-bestand mag maximaal 150.000 rijen hebben.</span><span class="sxs-lookup"><span data-stu-id="5ee88-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5ee88-361">Als de gegevens meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5ee88-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="5ee88-362">Tech-weergave in het rapport status van de telestroom</span><span class="sxs-lookup"><span data-stu-id="5ee88-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="5ee88-363">E-mail verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="5ee88-363">Sent and received email report</span></span>

<span data-ttu-id="5ee88-364">Het rapport **verzonden en ontvangen e-mail** is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spam detectie, malware en e-mailberichten die als ' goed ' worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="5ee88-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="5ee88-365">In dit rapport worden de volgende gegevens weergegeven: [dit rapport bevat](#mailflow-status-report) geen gegevens over berichten die worden geblokkeerd door de Edge-bescherming.</span><span class="sxs-lookup"><span data-stu-id="5ee88-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="5ee88-366">De weergave statistisch en de weergave Details van het rapport zijn van 90 dagen filteren toegestaan.</span><span class="sxs-lookup"><span data-stu-id="5ee88-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="5ee88-367">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **e-mail verzonden en ontvangen**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="5ee88-368">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget e-mail verzonden en ontvangen in het Dashboard rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="5ee88-370">Rapportweergave voor het verzonden en ontvangen e-mail rapport</span><span class="sxs-lookup"><span data-stu-id="5ee88-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="5ee88-371">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="5ee88-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="5ee88-372">**Opsplitst op: type**: de grafiek bevat alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="5ee88-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="5ee88-373">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-373">**Total**</span></span>
  - <span data-ttu-id="5ee88-374">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-374">**Good mail**</span></span>
  - <span data-ttu-id="5ee88-375">**Malware (anti malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="5ee88-376">**Detectie van spam**</span><span class="sxs-lookup"><span data-stu-id="5ee88-376">**Spam detections**</span></span>
  - <span data-ttu-id="5ee88-377">**Regel berichten**</span><span class="sxs-lookup"><span data-stu-id="5ee88-377">**Rule messages**</span></span>
  - <span data-ttu-id="5ee88-378">**Geavanceerde malware** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="5ee88-379">Wanneer u de muisaanwijzer op een dag (gegevenspunt) van de grafiek houdt, ziet u de gegevens voor die dag.</span><span class="sxs-lookup"><span data-stu-id="5ee88-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Type weergave in het rapport verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="5ee88-381">**Opsplitsen op: richting**: in de grafiek worden **totale**, **binnenkomende**en **uitgaande** gegevens weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5ee88-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="5ee88-382">Wanneer u de muisaanwijzer op een dag (gegevenspunt) van de grafiek houdt, ziet u de gegevens voor die dag.</span><span class="sxs-lookup"><span data-stu-id="5ee88-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![De weergaverichting in het rapport verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="5ee88-384">**Inzoomen op** \> **Malware (anti malware)**: met deze optie gaat u naar de [detectie van malware in een e-mail rapport](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="5ee88-385">**Inzoomen op** \> **Spam detectie)**: met deze optie gaat u naar het [rapport detectie van spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="5ee88-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="5ee88-386">Als u op **filters** in een rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="5ee88-387">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="5ee88-388">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-388">Direction values</span></span>
- <span data-ttu-id="5ee88-389">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="5ee88-389">Type values</span></span>

<span data-ttu-id="5ee88-390">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="5ee88-391">De tabel weergave Details voor het verzonden en ontvangen van een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="5ee88-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="5ee88-392">Als u klikt op **Details tabel weergeven** in de weergave van een oplopende **Volg** orde in: **richting** , wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5ee88-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="5ee88-393">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-393">**Date (UTC)**</span></span>
- <span data-ttu-id="5ee88-394">**Type**</span><span class="sxs-lookup"><span data-stu-id="5ee88-394">**Type**</span></span>
- <span data-ttu-id="5ee88-395">**Richting**</span><span class="sxs-lookup"><span data-stu-id="5ee88-395">**Direction**</span></span>
- <span data-ttu-id="5ee88-396">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="5ee88-396">**Message count**</span></span>

<span data-ttu-id="5ee88-397">Als u in een weergave met detail tabellen op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="5ee88-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="5ee88-398">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="5ee88-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="5ee88-399">Richtings waarden</span><span class="sxs-lookup"><span data-stu-id="5ee88-399">Direction values</span></span>
- <span data-ttu-id="5ee88-400">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="5ee88-400">Type values</span></span>

<span data-ttu-id="5ee88-401">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="5ee88-402">Rapport belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="5ee88-402">Top senders and recipients report</span></span>

<span data-ttu-id="5ee88-403">De **meest voorkomende afzenders en geadresseerden** zijn een cirkeldiagram met uw belangrijkste afzenders en geadresseerden voor e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="5ee88-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="5ee88-404">Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **Reports** \> **Dashboard** rapporten en selecteert u **belangrijkste afzenders en geadresseerden**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="5ee88-405">Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="5ee88-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Belangrijkste afzenders en widget geadresseerden in het Dashboard rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="5ee88-407">Rapportweergave voor het rapport meest afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="5ee88-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="5ee88-408">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="5ee88-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="5ee88-409">**Gegevens voor de \> belangrijkste afzenders weergeven**</span><span class="sxs-lookup"><span data-stu-id="5ee88-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="5ee88-410">**Gegevens weergeven voor geadresseerden van de \> belangrijkste e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="5ee88-411">**Gegevens voor de \> belangrijkste spam geadresseerden weergeven**</span><span class="sxs-lookup"><span data-stu-id="5ee88-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="5ee88-412">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="5ee88-413">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="5ee88-414">De compositie van het cirkeldiagram verandert op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="5ee88-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="5ee88-415">Wanneer u de muisaanwijzer boven een wig in het cirkeldiagram houdt, ziet u het aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="5ee88-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="5ee88-416">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="5ee88-418">Weergave Details voor het rapport belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="5ee88-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="5ee88-419">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="5ee88-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="5ee88-420">**Gegevens voor de \> belangrijkste afzenders weergeven**</span><span class="sxs-lookup"><span data-stu-id="5ee88-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="5ee88-421">**Belangrijkste afzenders van e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-421">**Top mail senders**</span></span>
  - <span data-ttu-id="5ee88-422">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-422">**Count**</span></span>

- <span data-ttu-id="5ee88-423">**Gegevens weergeven voor geadresseerden van de \> belangrijkste e-mail**</span><span class="sxs-lookup"><span data-stu-id="5ee88-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="5ee88-424">**Belangrijkste e-mail geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="5ee88-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="5ee88-425">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-425">**Count**</span></span>

- <span data-ttu-id="5ee88-426">**Gegevens voor de \> belangrijkste spam geadresseerden weergeven**</span><span class="sxs-lookup"><span data-stu-id="5ee88-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="5ee88-427">**Belangrijkste spam geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="5ee88-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="5ee88-428">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-428">**Count**</span></span>

- <span data-ttu-id="5ee88-429">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="5ee88-430">**Belangrijkste geadresseerden voor malware**</span><span class="sxs-lookup"><span data-stu-id="5ee88-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="5ee88-431">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-431">**Count**</span></span>

- <span data-ttu-id="5ee88-432">**Gegevens weergeven voor \> Belangrijkste geadresseerden voor malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="5ee88-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="5ee88-433">**Belangrijkste geadresseerden voor malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="5ee88-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="5ee88-434">**Getal**</span><span class="sxs-lookup"><span data-stu-id="5ee88-434">**Count**</span></span>

<span data-ttu-id="5ee88-435">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5ee88-436">Als u terug wilt gaan naar de rapportweergave, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5ee88-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="5ee88-437">Welke machtigingen zijn vereist voor het weergeven van deze rapporten?</span><span class="sxs-lookup"><span data-stu-id="5ee88-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="5ee88-438">Als u de rapporten wilt weergeven en gebruiken, moet u lid zijn van de opgegeven rollen groep in het beveiligings & nalevings centrum **en** in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ee88-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="5ee88-439">In het nalevings centrum beveiligings & moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="5ee88-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="5ee88-440">-Organisatiebeheer-beveiligingsbeheerder (u kunt dit ook doen in het [Azure Active Directory-beheercentrum](https://aad.portal.azure.com) -beveiligings lezer</span><span class="sxs-lookup"><span data-stu-id="5ee88-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="5ee88-441">Zie [Machtigingen in het Beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="5ee88-442">In Exchange Online moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="5ee88-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="5ee88-443">-Organisatiebeheer-alleen-bekijken Organisatiebeheer-alleen voor weergeven geadresseerden</span><span class="sxs-lookup"><span data-stu-id="5ee88-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="5ee88-444">Zie [machtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) en [rollen groepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ee88-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ee88-445">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5ee88-445">Related topics</span></span>

[<span data-ttu-id="5ee88-446">Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="5ee88-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="5ee88-447">E-mail stroom inzichten in het nalevings centrum voor beveiligings &</span><span class="sxs-lookup"><span data-stu-id="5ee88-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="5ee88-448">Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="5ee88-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="5ee88-449">Rapporten weergeven voor Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5ee88-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
