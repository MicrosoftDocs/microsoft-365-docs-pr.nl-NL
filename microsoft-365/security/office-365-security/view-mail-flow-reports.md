---
title: E-mailstroomrapporten weergeven in het Security & Compliance Center
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
description: Meer informatie over het zoeken en gebruiken van beveiligingsrapporten voor e-mailstromen voor uw organisatie. E-mailstroomrapporten zijn beschikbaar in het Security & Compliance Center.
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937180"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="eb25d-104">E-mailstroomrapporten weergeven in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="eb25d-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="eb25d-105">Naast de [e-mailstroominzichten](mail-flow-insights-v2.md) die beschikbaar zijn in het Security & Compliance Center, zijn er ook verschillende e-mailstroomrapporten beschikbaar om u te helpen uw Microsoft 365-organisatie te controleren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="eb25d-106">Als u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)beschikt, u deze rapporten bekijken in het Security & Compliance Center <https://office.protection.com> door naar Dashboard **Rapporten** te gaan \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="eb25d-107">Als u rechtstreeks naar het dashboard van rapporten wilt gaan, opent <https://office.protection.office.com/insightdashboard> u .</span><span class="sxs-lookup"><span data-stu-id="eb25d-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Dashboard Rapporten in het Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="eb25d-109">Connectorrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-109">Connector report</span></span>

<span data-ttu-id="eb25d-110">In **het rapport Connector** wordt de e-mailstroomactiviteit weergegeven op de [inkomende en uitgaande connectoren](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eb25d-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="eb25d-111">Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Rapportendashboard** \> **Dashboard** en selecteert u **Connector-rapport**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="eb25d-112">Open <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Object Connectorrapport in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="eb25d-114">Rapportweergave voor het connector-rapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-114">Report view for the Connector report</span></span>

<span data-ttu-id="eb25d-115">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="eb25d-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="eb25d-116">**Gegevens weergeven op: e-mailstroom**: Deze grafiek toont het aantal binnenkomende en uitgaande berichten, georganiseerd door:</span><span class="sxs-lookup"><span data-stu-id="eb25d-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="eb25d-117">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="eb25d-117">**Total**</span></span>
  - <span data-ttu-id="eb25d-118">**Van het internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="eb25d-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="eb25d-119">**Naar het internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="eb25d-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="eb25d-120">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="eb25d-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="eb25d-121">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de **gegevens weergeven voor** het besturingselement om een van deze opties of **Alle e-mailstroom**te selecteren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens per e-mailstroom weergeven in het connectorrapport](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="eb25d-123">**Gegevens weergeven door: TLS-gebruik**: deze grafiek toont het percentage TLS-versiegebruik (Transport Layer Security) voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="eb25d-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="eb25d-124">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de **gegevens weergeven voor** het besturingselement om een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="eb25d-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="eb25d-125">**Alle e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="eb25d-125">**All mail flow**</span></span>
  - <span data-ttu-id="eb25d-126">**Van het internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="eb25d-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="eb25d-127">**Naar het internet zonder connector**</span><span class="sxs-lookup"><span data-stu-id="eb25d-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="eb25d-128">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="eb25d-128">A specific connector that you've configured.</span></span>

  ![Gegevens weergeven op TLS-gebruik in het connector-rapport](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="eb25d-130">Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="eb25d-131">Tabelweergave Details voor het connectorrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-131">Details table view for the Connector report</span></span>

<span data-ttu-id="eb25d-132">Als u op **tabel Details weergeven** klikt in een rapportweergave, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eb25d-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="eb25d-133">**Datum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-133">**Date**</span></span>
- <span data-ttu-id="eb25d-134">**Verbindingsrichting en -naam**</span><span class="sxs-lookup"><span data-stu-id="eb25d-134">**Connector direction and name**</span></span>
- <span data-ttu-id="eb25d-135">**Connectortype**</span><span class="sxs-lookup"><span data-stu-id="eb25d-135">**Connector type**</span></span>
- <span data-ttu-id="eb25d-136">**Gedwongen TLS?**: De waarde **Waar** of **Onwaar**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="eb25d-137">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="eb25d-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="eb25d-138">**TLS 1.0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="eb25d-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="eb25d-139">**TLS 1.1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="eb25d-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="eb25d-140">**TLS 1.2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="eb25d-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="eb25d-141">**Volume**: Het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="eb25d-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="eb25d-142">Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb25d-143">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="eb25d-144">Rapport over de regel van exchange-transport</span><span class="sxs-lookup"><span data-stu-id="eb25d-144">Exchange transport rule report</span></span>

<span data-ttu-id="eb25d-145">Het **regelrapport Exchange-transport** bevat het effect van e-mailstroomregels (ook wel transportregels genoemd) op inkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eb25d-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="eb25d-146">Als u het rapport wilt bekijken, opent u het [Security & Compliance Center](https://protection.office.com), gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Exchange Transport-regel**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="eb25d-147">Open <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget Transportregel uitwisselen in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="eb25d-149">Rapportweergave voor het regelrapport Exchange-transport</span><span class="sxs-lookup"><span data-stu-id="eb25d-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="eb25d-150">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="eb25d-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="eb25d-151">**Gegevens bekijken door: Transportregels** \> uitwisselen **Uitsplitsen op: Richting**: Deze grafiek toont het aantal **binnenkomende** en **uitgaande** berichten dat door transportregels is beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="eb25d-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="eb25d-152">**Gegevens bekijken door: Transportregels** \> uitwisselen **Opsplitsen door: Ernst:** Deze grafiek toont het aantal **hoge ernst** en **gemiddelde ernst,** en **lage ernst** berichten.</span><span class="sxs-lookup"><span data-stu-id="eb25d-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="eb25d-153">U stelt het ernstniveau in als een actie in de regel **(Controleer deze regel met ernstniveau** of _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="eb25d-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="eb25d-154">Zie Acties van [de mailstroomregel in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb25d-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="eb25d-155">**Gegevens bekijken door: DLP Exchange-transportregels** \> **Uitsplitsen door: Richting**: Deze grafiek toont het aantal **binnenkomende** en **uitgaande** berichten die zijn beïnvloed door de transportregels voor gegevensverliespreventie (DLP).</span><span class="sxs-lookup"><span data-stu-id="eb25d-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="eb25d-156">U de grafiek verder verfijnen door de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="eb25d-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="eb25d-157">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="eb25d-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="eb25d-158">**Gegevens weergeven voor: gecompromitteerde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="eb25d-159">**Gegevens weergeven voor: Laag volume van de gedetecteerde inhoud us Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="eb25d-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="eb25d-160">**Gegevens bekijken door: DLP Exchange-transportregels** \> **Afbreken door: Richting**: Deze weergave toont het aantal **hoge ernst** en **gemiddelde ernst**en berichten met een lage **ernst** die zijn beïnvloed door DLP-transportregels.</span><span class="sxs-lookup"><span data-stu-id="eb25d-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="eb25d-161">U de grafiek verder verfijnen door de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="eb25d-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="eb25d-162">**Gegevens weergeven voor: alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="eb25d-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="eb25d-163">**Gegevens weergeven voor: gecompromitteerde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="eb25d-164">**Gegevens weergeven voor: Laag volume van de gedetecteerde inhoud us Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="eb25d-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="eb25d-165">Als u op **Filters** in een rapportweergave klikt, u de resultaten wijzigen met de volgende filters::</span><span class="sxs-lookup"><span data-stu-id="eb25d-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="eb25d-166">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb25d-167">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-167">Direction values</span></span>
- <span data-ttu-id="eb25d-168">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-168">Severity values</span></span>

![Rapportweergave in het regelrapport Exchange-transport](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="eb25d-170">Tabelweergave details voor het regelrapport Exchange-transport</span><span class="sxs-lookup"><span data-stu-id="eb25d-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="eb25d-171">Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:</span><span class="sxs-lookup"><span data-stu-id="eb25d-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="eb25d-172">**Gegevens bekijken door: Exchange Transport rules**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="eb25d-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-173">**Date**</span></span>
  - <span data-ttu-id="eb25d-174">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="eb25d-174">**Transport rule**</span></span>
  - <span data-ttu-id="eb25d-175">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="eb25d-175">**Subject**</span></span>
  - <span data-ttu-id="eb25d-176">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="eb25d-176">**Sender address**</span></span>
  - <span data-ttu-id="eb25d-177">**Adres van de geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="eb25d-177">**Recipient address**</span></span>
  - <span data-ttu-id="eb25d-178">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="eb25d-178">**Severity**</span></span>
  - <span data-ttu-id="eb25d-179">**Richting**</span><span class="sxs-lookup"><span data-stu-id="eb25d-179">**Direction**</span></span>

- <span data-ttu-id="eb25d-180">**Gegevens bekijken door: DLP Exchange transportregels**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="eb25d-181">**Datum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-181">**Date**</span></span>
  - <span data-ttu-id="eb25d-182">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="eb25d-182">**DLP policy**</span></span>
  - <span data-ttu-id="eb25d-183">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="eb25d-183">**Transport rule**</span></span>
  - <span data-ttu-id="eb25d-184">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="eb25d-184">**Subject**</span></span>
  - <span data-ttu-id="eb25d-185">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="eb25d-185">**Sender address**</span></span>
  - <span data-ttu-id="eb25d-186">**Adres van de geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="eb25d-186">**Recipient address**</span></span>
  - <span data-ttu-id="eb25d-187">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="eb25d-187">**Severity**</span></span>
  - <span data-ttu-id="eb25d-188">**Richting**</span><span class="sxs-lookup"><span data-stu-id="eb25d-188">**Direction**</span></span>

<span data-ttu-id="eb25d-189">Als u op **Filters** in een tabelweergave voor details klikt, u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="eb25d-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb25d-190">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb25d-191">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-191">Direction values</span></span>
- <span data-ttu-id="eb25d-192">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-192">Severity values</span></span>

<span data-ttu-id="eb25d-193">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="eb25d-194">Rapport doorsturen</span><span class="sxs-lookup"><span data-stu-id="eb25d-194">Forwarding report</span></span>

<span data-ttu-id="eb25d-195">In **het rapport Doorsturen** worden automatisch doorgestuurde berichten van uw organisatie weergegeven naar externe domeinen vanuit Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="eb25d-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="eb25d-196">Doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen en kunnen duiden op een gecompromitteerd account.</span><span class="sxs-lookup"><span data-stu-id="eb25d-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="eb25d-197">Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** en \> **Dashboard** selecteert u **Rapport Doorsturen**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="eb25d-198">Open <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Rapportobject doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="eb25d-200">Rapportweergave voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="eb25d-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="eb25d-201">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="eb25d-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb25d-202">**Gegevens weergeven voor: Doorstuurmethoden**: De volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eb25d-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="eb25d-203">**Transportregel**: Ook wel [regels voor e-mailstroom genoemd](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="eb25d-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="eb25d-204">**Postvakregel**: Ook wel [inboxregels genoemd](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="eb25d-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Weergave Methoden doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="eb25d-206">**Gegevens weergeven voor: Domeinen doorsturen**: in deze weergave worden de domeinen van de ontvanger weergegeven die de bestemmingen zijn voor doorsturen.</span><span class="sxs-lookup"><span data-stu-id="eb25d-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Domeinenweergave doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="eb25d-208">**Gegevens weergeven voor: Expediteurs**: De volgende expediteurs worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eb25d-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="eb25d-209">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="eb25d-209">**Transport rule**</span></span>
  - <span data-ttu-id="eb25d-210">Het postvak dat de regel Postvak IN bevat.</span><span class="sxs-lookup"><span data-stu-id="eb25d-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Weergave Doorstuuraars in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="eb25d-212">Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="eb25d-213">Tabelweergave Details voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="eb25d-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="eb25d-214">Als u op **tabel Details weergeven** klikt in een rapportweergave, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eb25d-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="eb25d-215">**Doorstuuraars**: de **regel waardetransport** of het postvak dat de regel Postvak IN doorstuurt.</span><span class="sxs-lookup"><span data-stu-id="eb25d-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="eb25d-216">**Type doorsturen**: de **regel waardepostvak** of **transportregel**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="eb25d-217">**Naam van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="eb25d-217">**Recipient name**</span></span>
- <span data-ttu-id="eb25d-218">**Geadresseerdendomein**</span><span class="sxs-lookup"><span data-stu-id="eb25d-218">**Recipient domain**</span></span>
- <span data-ttu-id="eb25d-219">**Details**: dit is de GUID-waarde van de e-mailstroomregel of de regelwaarde RuleIdentity van de regel Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="eb25d-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="eb25d-220">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-220">**Count**</span></span>
- <span data-ttu-id="eb25d-221">**Eerste termijn**</span><span class="sxs-lookup"><span data-stu-id="eb25d-221">**First forward date**</span></span>

<span data-ttu-id="eb25d-222">Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb25d-223">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="eb25d-224">Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-224">Mailflow status report</span></span>

<span data-ttu-id="eb25d-225">Het **e-mailstatusrapport** is vergelijkbaar met het [e-mailrapport Verzonden en ontvangen,](#sent-and-received-email-report)met aanvullende informatie over e-mail die is toegestaan of geblokkeerd op de rand.</span><span class="sxs-lookup"><span data-stu-id="eb25d-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="eb25d-226">Dit is het enige rapport dat randbeschermingsinformatie bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat deze wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="eb25d-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="eb25d-227">Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** en \> **Dashboard** selecteert u **het statusrapport van Mailflow**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="eb25d-228">Als u rechtstreeks naar het statusrapport Van de **e-mailstroom wilt**gaan, opent u <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Object Mailflow-statusrapport in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="eb25d-230">Tekstweergave voor het statusrapport Mailflow</span><span class="sxs-lookup"><span data-stu-id="eb25d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="eb25d-231">Wanneer u het rapport opent, wordt het tabblad **Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="eb25d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="eb25d-232">Standaard bevat deze weergave een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="eb25d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="eb25d-233">**Datum**: De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="eb25d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="eb25d-234">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-234">**Direction**:</span></span>

  - <span data-ttu-id="eb25d-235">**Inkomende**</span><span class="sxs-lookup"><span data-stu-id="eb25d-235">**Inbound**</span></span>
  - <span data-ttu-id="eb25d-236">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="eb25d-236">**Outbound**</span></span>
  - <span data-ttu-id="eb25d-237">**Intra-org** (apart geteld van **Inbound** en **Outbound)**</span><span class="sxs-lookup"><span data-stu-id="eb25d-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="eb25d-238">**Type**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-238">**Type**:</span></span>

  - <span data-ttu-id="eb25d-239">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="eb25d-239">**Good mail**</span></span>
  - <span data-ttu-id="eb25d-240">**Malware**</span><span class="sxs-lookup"><span data-stu-id="eb25d-240">**Malware**</span></span>
  - <span data-ttu-id="eb25d-241">**Spam**</span><span class="sxs-lookup"><span data-stu-id="eb25d-241">**Spam**</span></span>
  - <span data-ttu-id="eb25d-242">**Randbescherming**</span><span class="sxs-lookup"><span data-stu-id="eb25d-242">**Edge protection**</span></span>
  - <span data-ttu-id="eb25d-243">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="eb25d-243">**Rule messages**</span></span>
  - <span data-ttu-id="eb25d-244">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="eb25d-244">**Phishing email**</span></span>

<span data-ttu-id="eb25d-245">De grafiek wordt georganiseerd door de **waarden type.**</span><span class="sxs-lookup"><span data-stu-id="eb25d-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="eb25d-246">U deze filters wijzigen door op **Filter** te klikken of door op een waarde in de grafieklegenda te klikken.</span><span class="sxs-lookup"><span data-stu-id="eb25d-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="eb25d-247">De gegevenstabel bevat de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="eb25d-247">The data table contains the following information:</span></span>

- <span data-ttu-id="eb25d-248">**Richting**</span><span class="sxs-lookup"><span data-stu-id="eb25d-248">**Direction**</span></span>
- <span data-ttu-id="eb25d-249">**Type**</span><span class="sxs-lookup"><span data-stu-id="eb25d-249">**Type**</span></span>
- <span data-ttu-id="eb25d-250">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="eb25d-250">**24 hours**</span></span>
- <span data-ttu-id="eb25d-251">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-251">**3 days**</span></span>
- <span data-ttu-id="eb25d-252">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-252">**7 days**</span></span>
- <span data-ttu-id="eb25d-253">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-253">**15 days**</span></span>
- <span data-ttu-id="eb25d-254">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-254">**30 days**</span></span>

<span data-ttu-id="eb25d-255">Als u op **Een categorie kiezen voor meer details**klikt, u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="eb25d-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="eb25d-256">**Phishing-e-mail:** deze selectie neemt u mee naar het [statusrapport bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="eb25d-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="eb25d-257">**Malware in e-mail**: Deze selectie neemt u mee naar het [statusrapport bedreigingsbescherming.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="eb25d-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="eb25d-258">**Spamdetecties**: Deze selectie neemt u mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="eb25d-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="eb25d-259">**Edge geblokkeerde spam**: Deze selectie neemt je mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="eb25d-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="eb25d-260">**Uitvoer**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-260">**Export**:</span></span>

<span data-ttu-id="eb25d-261">Voor de detailweergave u alleen gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="eb25d-262">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="eb25d-263">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="eb25d-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="eb25d-264">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="eb25d-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="eb25d-265">Tekstweergave in het statusrapport Mailflow</span><span class="sxs-lookup"><span data-stu-id="eb25d-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="eb25d-266">Richtingsweergave voor het estroomstatusrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="eb25d-267">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters in de weergave **Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="eb25d-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="eb25d-268">De grafiek wordt georganiseerd op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="eb25d-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="eb25d-269">U deze filters wijzigen door op **Filter** te klikken of door op een waarde in de grafieklegenda te klikken.</span><span class="sxs-lookup"><span data-stu-id="eb25d-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="eb25d-270">Dezelfde filters uit de weergave **Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="eb25d-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="eb25d-271">De gegevenstabel bevat dezelfde informatie uit de weergave **Type.**</span><span class="sxs-lookup"><span data-stu-id="eb25d-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="eb25d-272">De **categorie Een categorie kiezen voor meer details beschikbare** selecties en gedrag zijn hetzelfde als de weergave **Type.**</span><span class="sxs-lookup"><span data-stu-id="eb25d-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="eb25d-273">**Uitvoer**:</span><span class="sxs-lookup"><span data-stu-id="eb25d-273">**Export**:</span></span>

<span data-ttu-id="eb25d-274">Voor de detailweergave u alleen gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="eb25d-275">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="eb25d-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="eb25d-276">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="eb25d-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="eb25d-277">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="eb25d-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="eb25d-278">Richtingsweergave in het estroomstatusrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="eb25d-279">Verzonden en ontvangen e-mailrapport</span><span class="sxs-lookup"><span data-stu-id="eb25d-279">Sent and received email report</span></span>

<span data-ttu-id="eb25d-280">Het **verzonden en ontvangen e-mailrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spamdetecties, malware en e-mail die als 'goed' zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="eb25d-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="eb25d-281">Het verschil tussen dit rapport en het [e-mailstatusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="eb25d-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="eb25d-282">De totaalweergave en de detailweergave van het rapport maken 90 dagen filteren mogelijk.</span><span class="sxs-lookup"><span data-stu-id="eb25d-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="eb25d-283">Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** \> **Dashboard** en selecteert u **Verzonden en ontvangen e-mail**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="eb25d-284">Open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Verzonden en ontvangen e-mailwidget in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="eb25d-286">Rapportweergave voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="eb25d-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="eb25d-287">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="eb25d-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb25d-288">**Uitsplitsen op: Tekst:** De grafiek toont alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="eb25d-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="eb25d-289">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="eb25d-289">**Total**</span></span>
  - <span data-ttu-id="eb25d-290">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="eb25d-290">**Good mail**</span></span>
  - <span data-ttu-id="eb25d-291">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="eb25d-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="eb25d-292">**Spamdetecties**</span><span class="sxs-lookup"><span data-stu-id="eb25d-292">**Spam detections**</span></span>
  - <span data-ttu-id="eb25d-293">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="eb25d-293">**Rule messages**</span></span>
  - <span data-ttu-id="eb25d-294">**Geavanceerde malware** (AtP voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="eb25d-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="eb25d-295">Wanneer u gedurende een dag (gegevenspunt) in de grafiek houdt, u details voor die dag zien.</span><span class="sxs-lookup"><span data-stu-id="eb25d-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Typ weergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="eb25d-297">**Uitsplitsen op: Richting**: De grafiek toont **totaal-** en **binnenkomende**en **uitgaande** gegevens.</span><span class="sxs-lookup"><span data-stu-id="eb25d-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="eb25d-298">Wanneer u gedurende een dag (gegevenspunt) in de grafiek houdt, u details voor die dag zien.</span><span class="sxs-lookup"><span data-stu-id="eb25d-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtingsweergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="eb25d-300">**Inzoomen op** \> **Malware (anti-malware)**: Deze selectie neemt u mee naar de [malware detectie in e-mail rapport](view-email-security-reports.md#malware-detection-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="eb25d-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detection in email report](view-email-security-reports.md#malware-detection-in-email-report).</span></span>

- <span data-ttu-id="eb25d-301">**Inzoomen op** \> **Spamdetecties)**: Deze selectie neemt je mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="eb25d-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="eb25d-302">Als u op **Filters** in een rapportweergave klikt, u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="eb25d-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb25d-303">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb25d-304">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-304">Direction values</span></span>
- <span data-ttu-id="eb25d-305">Tekstwaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-305">Type values</span></span>

<span data-ttu-id="eb25d-306">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="eb25d-307">Tabelweergave details voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="eb25d-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="eb25d-308">Als u op **Tabel Details weergeven** klikt in de **tabel Uitsplitsen door: Richting** of **Opsplitsen door:** Richtingsweergave, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eb25d-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="eb25d-309">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="eb25d-309">**Date (UTC)**</span></span>
- <span data-ttu-id="eb25d-310">**Type**</span><span class="sxs-lookup"><span data-stu-id="eb25d-310">**Type**</span></span>
- <span data-ttu-id="eb25d-311">**Richting**</span><span class="sxs-lookup"><span data-stu-id="eb25d-311">**Direction**</span></span>
- <span data-ttu-id="eb25d-312">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="eb25d-312">**Message count**</span></span>

<span data-ttu-id="eb25d-313">Als u op **Filters** in een tabelweergave voor details klikt, u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="eb25d-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="eb25d-314">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="eb25d-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="eb25d-315">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-315">Direction values</span></span>
- <span data-ttu-id="eb25d-316">Tekstwaarden</span><span class="sxs-lookup"><span data-stu-id="eb25d-316">Type values</span></span>

<span data-ttu-id="eb25d-317">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="eb25d-318">Rapport Top afzenders en ontvangers</span><span class="sxs-lookup"><span data-stu-id="eb25d-318">Top senders and recipients report</span></span>

<span data-ttu-id="eb25d-319">Het rapport **Top afzenders en geadresseerden** is een cirkeldiagram met uw beste e-mail afzenders en ontvangers.</span><span class="sxs-lookup"><span data-stu-id="eb25d-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="eb25d-320">Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Top afzenders en ontvangers**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="eb25d-321">Open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="eb25d-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Top afzenders en geadresseerden in het dashboard Rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="eb25d-323">Rapportweergave voor het rapport Top afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="eb25d-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="eb25d-324">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="eb25d-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="eb25d-325">**Gegevens weergeven voor \> topmailzenders**</span><span class="sxs-lookup"><span data-stu-id="eb25d-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="eb25d-326">**Gegevens weergeven voor \> tope-mailontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="eb25d-327">**Gegevens weergeven voor \> topspamontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="eb25d-328">**Gegevens weergeven voor \> Top malware ontvangers** (EOP)</span><span class="sxs-lookup"><span data-stu-id="eb25d-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="eb25d-329">**Gegevens weergeven voor \> Top malware ontvangers (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="eb25d-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="eb25d-330">De samenstelling van het cirkeldiagram wordt gewijzigd op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="eb25d-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="eb25d-331">Wanneer u over een wig in het cirkeldiagram beweegt, ziet u een aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="eb25d-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="eb25d-332">Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport Top afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="eb25d-334">Tabelweergave details voor het rapport Top afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="eb25d-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="eb25d-335">Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:</span><span class="sxs-lookup"><span data-stu-id="eb25d-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="eb25d-336">**Gegevens weergeven voor \> topmailzenders**</span><span class="sxs-lookup"><span data-stu-id="eb25d-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="eb25d-337">**Top e-mail afzenders**</span><span class="sxs-lookup"><span data-stu-id="eb25d-337">**Top mail senders**</span></span>
  - <span data-ttu-id="eb25d-338">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-338">**Count**</span></span>

- <span data-ttu-id="eb25d-339">**Gegevens weergeven voor \> tope-mailontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="eb25d-340">**Topontvangers voor e-mail**</span><span class="sxs-lookup"><span data-stu-id="eb25d-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="eb25d-341">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-341">**Count**</span></span>

- <span data-ttu-id="eb25d-342">**Gegevens weergeven voor \> topspamontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="eb25d-343">**Top spam ontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="eb25d-344">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-344">**Count**</span></span>

- <span data-ttu-id="eb25d-345">**Gegevens weergeven voor \> Top malware ontvangers** (EOP)</span><span class="sxs-lookup"><span data-stu-id="eb25d-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="eb25d-346">**Top malware ontvangers**</span><span class="sxs-lookup"><span data-stu-id="eb25d-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="eb25d-347">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-347">**Count**</span></span>

- <span data-ttu-id="eb25d-348">**Gegevens weergeven voor \> Top malware ontvangers (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="eb25d-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="eb25d-349">**Top malware ontvangers (ATP)**</span><span class="sxs-lookup"><span data-stu-id="eb25d-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="eb25d-350">**Tellen**</span><span class="sxs-lookup"><span data-stu-id="eb25d-350">**Count**</span></span>

<span data-ttu-id="eb25d-351">Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="eb25d-352">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="eb25d-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="eb25d-353">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="eb25d-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="eb25d-354">Als u de rapporten wilt weergeven en gebruiken, moet u lid zijn van de opgegeven rolgroep in het Security & Compliance Center **en** in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eb25d-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="eb25d-355">In het Security & Compliance Center moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="eb25d-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="eb25d-356">-Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="eb25d-356">-Organization Management</span></span>

  <span data-ttu-id="eb25d-357">-Beveiligingsbeheerder (u dit ook doen in het [Azure Active Directory-beheercentrum](https://aad.portal.azure.com) -Security Reader</span><span class="sxs-lookup"><span data-stu-id="eb25d-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="eb25d-358">Zie [Machtigingen in het Beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb25d-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="eb25d-359">In Exchange Online moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="eb25d-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="eb25d-360">-Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="eb25d-360">-Organization Management</span></span>

  <span data-ttu-id="eb25d-361">-Alleen-weergeven organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="eb25d-361">-View-only Organization Management</span></span>

  <span data-ttu-id="eb25d-362">-Ontvangers alleen weergeven</span><span class="sxs-lookup"><span data-stu-id="eb25d-362">-View-Only Recipients</span></span>

  <span data-ttu-id="eb25d-363">-Compliance Management</span><span class="sxs-lookup"><span data-stu-id="eb25d-363">-Compliance Management</span></span>

<span data-ttu-id="eb25d-364">Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) en [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eb25d-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb25d-365">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="eb25d-365">Related topics</span></span>

[<span data-ttu-id="eb25d-366">Slimme rapporten en inzichten in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="eb25d-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="eb25d-367">E-mailbeveiligingsrapporten weergeven in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="eb25d-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
