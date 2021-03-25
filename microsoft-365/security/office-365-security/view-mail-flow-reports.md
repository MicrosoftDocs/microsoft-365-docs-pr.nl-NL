---
title: E-mailstroomrapporten weergeven in het dashboard Rapporten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de e-mailstroomrapporten die beschikbaar zijn in het dashboard Rapporten in & Compliancecentrum.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13871908c3b09660906b9233d23495830cf31ba9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204505"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="e30f0-103">E-mailstroomrapporten weergeven in het dashboard Rapporten in & Compliance center</span><span class="sxs-lookup"><span data-stu-id="e30f0-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e30f0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e30f0-104">**Applies to**</span></span>
- [<span data-ttu-id="e30f0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e30f0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e30f0-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e30f0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e30f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e30f0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e30f0-108">Naast de e-mailstroomrapporten die [](mail-flow-insights-v2.md) beschikbaar zijn in het e-mailstroomdashboard in het beveiligings- & compliancecentrum, zijn er diverse extra e-mailstroomrapporten beschikbaar in het dashboard Rapporten om u te helpen uw Microsoft 365-organisatie te controleren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="e30f0-109">Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het Beveiligings- & [compliancecentrum](https://protection.office.com) door naar **Rapportendashboard te** \> **gaan.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e30f0-110">Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Rapportendashboard in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="e30f0-112">Connectorrapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-112">Connector report</span></span>

<span data-ttu-id="e30f0-113">Het **rapport Connector toont** e-mailstroomactiviteit op de binnenkomende en uitgaande [verbindingslijnen](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e30f0-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="e30f0-114">Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en selecteert u **Connector-rapport.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="e30f0-115">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorrapportwidget in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="e30f0-117">Rapportweergave voor het connectorrapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-117">Report view for the Connector report</span></span>

<span data-ttu-id="e30f0-118">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="e30f0-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="e30f0-119">**Gegevens weergeven op: E-mailstroom:** In deze grafiek ziet u het aantal binnenkomende en uitgaande berichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="e30f0-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="e30f0-120">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-120">**Total**</span></span>
  - <span data-ttu-id="e30f0-121">**Van internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="e30f0-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e30f0-122">**Naar internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="e30f0-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e30f0-123">Een specifieke verbindingslijn die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="e30f0-124">Als u de gegevens in de grafiek wilt isoleren, gebruikt u gegevens **voor** besturingselementen tonen om een van deze opties of **Alle e-mailstroom te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens per e-mailstroom weergeven in het connectorrapport](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="e30f0-126">**Gegevens weergeven op: TLS-gebruik:** In deze grafiek wordt het percentage TLS-versiegebruik (Transport Layer Security) voor e-mailstroom weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e30f0-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="e30f0-127">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de optie Gegevens **voor besturingselementen** tonen om een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="e30f0-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="e30f0-128">**Alle e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="e30f0-128">**All mail flow**</span></span>
  - <span data-ttu-id="e30f0-129">**Van internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="e30f0-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e30f0-130">**Naar internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="e30f0-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e30f0-131">Een specifieke verbindingslijn die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-131">A specific connector that you've configured.</span></span>

  ![Gegevens weergeven op TLS-gebruik in het connectorrapport](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="e30f0-133">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="e30f0-134">Detailtabelweergave voor het connectorrapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-134">Details table view for the Connector report</span></span>

<span data-ttu-id="e30f0-135">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e30f0-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e30f0-136">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-136">**Date**</span></span>
- <span data-ttu-id="e30f0-137">**Richting en naam van verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="e30f0-137">**Connector direction and name**</span></span>
- <span data-ttu-id="e30f0-138">**Connectortype**</span><span class="sxs-lookup"><span data-stu-id="e30f0-138">**Connector type**</span></span>
- <span data-ttu-id="e30f0-139">**Gedwongen TLS?**: De waarde **Waar** of **Onwaar**.</span><span class="sxs-lookup"><span data-stu-id="e30f0-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="e30f0-140">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="e30f0-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="e30f0-141">**TLS 1,0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="e30f0-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="e30f0-142">**TLS 1,1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="e30f0-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="e30f0-143">**TLS 1,2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="e30f0-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="e30f0-144">**Volume:** Het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="e30f0-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="e30f0-145">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e30f0-146">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="e30f0-147">Rapport met exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="e30f0-147">Exchange transport rule report</span></span>

<span data-ttu-id="e30f0-148">Het **rapport Exchange-transportregel toont** het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e30f0-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="e30f0-149">Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en **selecteert u Exchange Transport-regel**.</span><span class="sxs-lookup"><span data-stu-id="e30f0-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="e30f0-150">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-transportregelwidget in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e30f0-152">Rapportweergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="e30f0-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="e30f0-153">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="e30f0-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="e30f0-154">**Gegevens weergeven op: Exchange-transportregels** \> **Afbreed door: Richting:** In deze grafiek  ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door transportregels.</span><span class="sxs-lookup"><span data-stu-id="e30f0-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="e30f0-155">**Gegevens weergeven op: Exchange-transportregels** \> **Afbreed door: Ernst:** In deze  grafiek ziet u het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een **lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="e30f0-156">U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="e30f0-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="e30f0-157">Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="e30f0-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="e30f0-158">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Afbreiding door: Richting:** In deze  grafiek ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door DLP-transportregels (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="e30f0-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="e30f0-159">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="e30f0-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e30f0-160">**Gegevens voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="e30f0-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e30f0-161">**Gegevens voor: Gecompromitteerd gebruikers**</span><span class="sxs-lookup"><span data-stu-id="e30f0-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e30f0-162">**Gegevens voor: Laag volume aan gedetecteerde Amerikaanse Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e30f0-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="e30f0-163">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Afbreiding door: Richting:** In  deze weergave ziet u  het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een lage ernst die zijn beïnvloed door DLP-transportregels.</span><span class="sxs-lookup"><span data-stu-id="e30f0-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="e30f0-164">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="e30f0-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e30f0-165">**Gegevens voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="e30f0-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e30f0-166">**Gegevens voor: Gecompromitteerd gebruikers**</span><span class="sxs-lookup"><span data-stu-id="e30f0-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e30f0-167">**Gegevens voor: Laag volume aan gedetecteerde Amerikaanse Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="e30f0-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="e30f0-168">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters::</span><span class="sxs-lookup"><span data-stu-id="e30f0-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="e30f0-169">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="e30f0-170">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-170">Direction values</span></span>
- <span data-ttu-id="e30f0-171">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-171">Severity values</span></span>

![Rapportweergave in het rapport Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e30f0-173">Tabelweergave Details voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="e30f0-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="e30f0-174">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="e30f0-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e30f0-175">**Gegevens weergeven door: Exchange-transportregels:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="e30f0-176">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-176">**Date**</span></span>
  - <span data-ttu-id="e30f0-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e30f0-177">**Transport rule**</span></span>
  - <span data-ttu-id="e30f0-178">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="e30f0-178">**Subject**</span></span>
  - <span data-ttu-id="e30f0-179">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="e30f0-179">**Sender address**</span></span>
  - <span data-ttu-id="e30f0-180">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="e30f0-180">**Recipient address**</span></span>
  - <span data-ttu-id="e30f0-181">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="e30f0-181">**Severity**</span></span>
  - <span data-ttu-id="e30f0-182">**Richting**</span><span class="sxs-lookup"><span data-stu-id="e30f0-182">**Direction**</span></span>

- <span data-ttu-id="e30f0-183">**Gegevens weergeven op: DLP Exchange-transportregels**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="e30f0-184">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-184">**Date**</span></span>
  - <span data-ttu-id="e30f0-185">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="e30f0-185">**DLP policy**</span></span>
  - <span data-ttu-id="e30f0-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e30f0-186">**Transport rule**</span></span>
  - <span data-ttu-id="e30f0-187">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="e30f0-187">**Subject**</span></span>
  - <span data-ttu-id="e30f0-188">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="e30f0-188">**Sender address**</span></span>
  - <span data-ttu-id="e30f0-189">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="e30f0-189">**Recipient address**</span></span>
  - <span data-ttu-id="e30f0-190">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="e30f0-190">**Severity**</span></span>
  - <span data-ttu-id="e30f0-191">**Richting**</span><span class="sxs-lookup"><span data-stu-id="e30f0-191">**Direction**</span></span>

<span data-ttu-id="e30f0-192">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e30f0-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e30f0-193">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="e30f0-194">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-194">Direction values</span></span>
- <span data-ttu-id="e30f0-195">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-195">Severity values</span></span>

<span data-ttu-id="e30f0-196">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="e30f0-197">Doorsturen van rapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-197">Forwarding report</span></span>

<span data-ttu-id="e30f0-198">In **het rapport Doorsturen** ziet u de automatisch doorgestuurde berichten van uw organisatie naar externe domeinen vanuit Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="e30f0-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="e30f0-199">Doorgestuurde berichten kunnen een beveiligings- of compliancerisico opleveren en kunnen een gekromd account aangeven.</span><span class="sxs-lookup"><span data-stu-id="e30f0-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="e30f0-200">Als u het rapport wilt bekijken, opent u  het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en selecteert u **Rapport doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="e30f0-201">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Rapportwidget doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="e30f0-203">Rapportweergave voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="e30f0-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="e30f0-204">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="e30f0-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e30f0-205">**Gegevens voor: Doorsturen methoden**: De volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e30f0-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="e30f0-206">**Transportregel:** ook wel [e-mailstroomregels genoemd.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e30f0-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="e30f0-207">**Postvakregel:** Ook wel regels [voor Postvak IN genoemd.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="e30f0-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![De weergave Doorsturen van methoden in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="e30f0-209">**Gegevens weergeven voor: Domeinen doorsturen:** in deze weergave ziet u de geadresseerdedomeinen die de bestemmingen zijn voor doorsturen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![De weergave Domeinen doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="e30f0-211">**Gegevens voor: Doorsturen:** De volgende doorsturen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e30f0-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="e30f0-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="e30f0-212">**Transport rule**</span></span>
  - <span data-ttu-id="e30f0-213">Het postvak met de regel Postvak IN doorsturen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![De weergave Doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="e30f0-215">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="e30f0-216">Tabelweergave Details voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="e30f0-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="e30f0-217">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e30f0-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e30f0-218">**Doorst:De** waarde **Transportregel** of het postvak met de regel Postvak IN doorsturen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="e30f0-219">**Doorsturen:** De waarde **Regel Postvak** of **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="e30f0-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="e30f0-220">**Naam van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="e30f0-220">**Recipient name**</span></span>
- <span data-ttu-id="e30f0-221">**Domein geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="e30f0-221">**Recipient domain**</span></span>
- <span data-ttu-id="e30f0-222">**Details:** dit is de GUID-waarde van de e-mailstroomregel of de waarde RuleIdentity van de regel Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="e30f0-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="e30f0-223">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-223">**Count**</span></span>
- <span data-ttu-id="e30f0-224">**Eerste doorgestuurde datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-224">**First forward date**</span></span>

<span data-ttu-id="e30f0-225">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e30f0-226">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e30f0-227">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-227">Mailflow status report</span></span>

<span data-ttu-id="e30f0-228">Het **rapport Mailflow-status** is vergelijkbaar met het e-mailrapport Verzonden en [ontvangen,](#sent-and-received-email-report)met aanvullende informatie over e-mail die aan de rand is toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="e30f0-229">Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat e-mail wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e30f0-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e30f0-230">Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="e30f0-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="e30f0-231">Als u het rapport wilt bekijken, opent u  het [beveiligingscentrum & compliancecentrum,](https://protection.office.com)gaat u naar Het dashboard Rapporten en selecteert u \>  **Mailflow-statusrapport.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="e30f0-232">Als u rechtstreeks naar het rapport **E-mailstroomstatus wilt gaan,** opent <https://protection.office.com/mailflowStatusReport> u .</span><span class="sxs-lookup"><span data-stu-id="e30f0-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Rapportwidget Mailflow-status in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="e30f0-234">Typweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="e30f0-235">Wanneer u het rapport opent, is **het tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="e30f0-236">Standaard bevat deze weergave een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="e30f0-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e30f0-237">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="e30f0-238">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-238">**Direction**:</span></span>

  - <span data-ttu-id="e30f0-239">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="e30f0-239">**Inbound**</span></span>
  - <span data-ttu-id="e30f0-240">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="e30f0-240">**Outbound**</span></span>
  - <span data-ttu-id="e30f0-241">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="e30f0-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e30f0-242">afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="e30f0-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="e30f0-243">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-243">**Type**:</span></span>

  - <span data-ttu-id="e30f0-244">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-244">**Good mail**</span></span>
  - <span data-ttu-id="e30f0-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="e30f0-245">**Malware**</span></span>
  - <span data-ttu-id="e30f0-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="e30f0-246">**Spam**</span></span>
  - <span data-ttu-id="e30f0-247">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="e30f0-247">**Edge protection**</span></span>
  - <span data-ttu-id="e30f0-248">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="e30f0-248">**Rule messages**</span></span>
  - <span data-ttu-id="e30f0-249">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-249">**Phishing email**</span></span>

<span data-ttu-id="e30f0-250">De grafiek wordt ingedeeld op basis van **de waarden Type.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="e30f0-251">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="e30f0-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="e30f0-252">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="e30f0-252">The data table contains the following information:</span></span>

- <span data-ttu-id="e30f0-253">**Richting**</span><span class="sxs-lookup"><span data-stu-id="e30f0-253">**Direction**</span></span>
- <span data-ttu-id="e30f0-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="e30f0-254">**Type**</span></span>
- <span data-ttu-id="e30f0-255">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="e30f0-255">**24 hours**</span></span>
- <span data-ttu-id="e30f0-256">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-256">**3 days**</span></span>
- <span data-ttu-id="e30f0-257">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-257">**7 days**</span></span>
- <span data-ttu-id="e30f0-258">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-258">**15 days**</span></span>
- <span data-ttu-id="e30f0-259">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-259">**30 days**</span></span>

<span data-ttu-id="e30f0-260">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="e30f0-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="e30f0-261">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e30f0-262">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e30f0-263">**Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="e30f0-264">**Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e30f0-265">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-265">**Export**:</span></span>

<span data-ttu-id="e30f0-266">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e30f0-267">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e30f0-268">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e30f0-269">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e30f0-270">Weergave typen in het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="e30f0-271">Richtingsweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="e30f0-272">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="e30f0-273">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="e30f0-274">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="e30f0-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="e30f0-275">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="e30f0-276">De gegevenstabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="e30f0-277">De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.</span><span class="sxs-lookup"><span data-stu-id="e30f0-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="e30f0-278">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-278">**Export**:</span></span>

<span data-ttu-id="e30f0-279">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e30f0-280">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e30f0-281">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e30f0-282">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e30f0-283">Richtingsweergave in het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="e30f0-284">Trechterweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="e30f0-285">In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="e30f0-286">Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="e30f0-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="e30f0-287">Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="e30f0-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e30f0-288">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e30f0-289">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-289">**Direction**:</span></span>

  - <span data-ttu-id="e30f0-290">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="e30f0-290">**Inbound**</span></span>
  - <span data-ttu-id="e30f0-291">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="e30f0-291">**Outbound**</span></span>
  - <span data-ttu-id="e30f0-292">**Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).</span><span class="sxs-lookup"><span data-stu-id="e30f0-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="e30f0-293">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e30f0-294">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e30f0-295">In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="e30f0-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="e30f0-296">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-296">**Total email**</span></span>
- <span data-ttu-id="e30f0-297">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="e30f0-297">**Email after edge protection**</span></span>
- <span data-ttu-id="e30f0-298">**E-mail na anti-malware, bestandsreputatie, bestandstypeblok**</span><span class="sxs-lookup"><span data-stu-id="e30f0-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="e30f0-299">**E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="e30f0-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="e30f0-300">**E-mail na antispam, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="e30f0-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="e30f0-301">**E-mail na gebruikers- en domein-imitatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e30f0-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="e30f0-302">**E-mail na bestand en URL-detonatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e30f0-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="e30f0-303">**E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="e30f0-304"><sup>Alleen 1</sup> Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e30f0-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="e30f0-305">Als u het e-mailbericht dat is gefilterd op EOP of Defender voor Office 365 afzonderlijk wilt weergeven, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="e30f0-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="e30f0-306">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="e30f0-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e30f0-307">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-307">**Date**</span></span>
- <span data-ttu-id="e30f0-308">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-308">**Total email**</span></span>
- <span data-ttu-id="e30f0-309">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="e30f0-309">**Edge protection**</span></span>
- <span data-ttu-id="e30f0-310">**Anti-malware, bestandsreputatie, bestandstypeblok:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="e30f0-311">**Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="e30f0-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="e30f0-312">**Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="e30f0-313">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="e30f0-314">**URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="e30f0-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="e30f0-315">**Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.</span><span class="sxs-lookup"><span data-stu-id="e30f0-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="e30f0-316">**Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.</span><span class="sxs-lookup"><span data-stu-id="e30f0-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="e30f0-317">**Antispam, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="e30f0-318">**Bulkmailfilters:** Berichten die zijn gefilterd als gevolg van een poging om bulkmail bij de geadresseerden te bezorgen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="e30f0-319">**Gebruikers- en domein-imitatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e30f0-320">**Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="e30f0-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="e30f0-321">**Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="e30f0-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="e30f0-322">**Bestands- en URL-detonatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e30f0-323">**Bestandsdetonatie:** berichten gefilterd met een beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="e30f0-324">**URL-detonatie:** bericht gefilterd door een beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="e30f0-325">**Beveiliging na aflevering en ZAP (ATP) of ZAP (EOP)**: ZAP geeft automatisch nul uur aan.</span><span class="sxs-lookup"><span data-stu-id="e30f0-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="e30f0-326">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="e30f0-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e30f0-327">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-327">**Export**:</span></span>

<span data-ttu-id="e30f0-328">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="e30f0-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="e30f0-329">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e30f0-330">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e30f0-331">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e30f0-332">Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="e30f0-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e30f0-333">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e30f0-334">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e30f0-335">Trechterweergave in het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="e30f0-336">Technische weergave voor het mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="e30f0-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="e30f0-337">De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="e30f0-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="e30f0-338">In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="e30f0-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="e30f0-339">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="e30f0-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e30f0-340">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e30f0-341">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-341">**Direction**:</span></span>

  - <span data-ttu-id="e30f0-342">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="e30f0-342">**Inbound**</span></span>
  - <span data-ttu-id="e30f0-343">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="e30f0-343">**Outbound**</span></span>
  - <span data-ttu-id="e30f0-344">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="e30f0-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e30f0-345">afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)</span><span class="sxs-lookup"><span data-stu-id="e30f0-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="e30f0-346">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e30f0-347">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e30f0-348">In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="e30f0-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="e30f0-349">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-349">**Total email**</span></span>
- <span data-ttu-id="e30f0-350">**Rand toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="e30f0-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="e30f0-351">**Geen malware,** **detectie van veilige bijlagen,** <sup>\*</sup> detectie van **anti-malwareprogramma's** en **regelberichten**</span><span class="sxs-lookup"><span data-stu-id="e30f0-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="e30f0-352">**Geen phish,** **DMARC-fout,** **imitatiedetectie,** **spoofdetectie** en **Phish-detectie**</span><span class="sxs-lookup"><span data-stu-id="e30f0-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="e30f0-353">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e30f0-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="e30f0-354">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="e30f0-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="e30f0-355">**Niet-schadelijke e-mail,** **detectie van** veilige koppelingen <sup>\*</sup> en **ZAP**</span><span class="sxs-lookup"><span data-stu-id="e30f0-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="e30f0-356"><sup>\*</sup> Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e30f0-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="e30f0-357">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.</span><span class="sxs-lookup"><span data-stu-id="e30f0-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="e30f0-358">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="e30f0-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e30f0-359">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-359">**Date**</span></span>
- <span data-ttu-id="e30f0-360">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-360">**Total email**</span></span>
- <span data-ttu-id="e30f0-361">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="e30f0-361">**Edge filtered**</span></span>
- <span data-ttu-id="e30f0-362">**Anti-malware-engine, Veilige bijlagen, regel gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="e30f0-363">**Regel gefilterd:** Berichten gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="e30f0-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="e30f0-364">**DMARC, imitatie, spoof, phish gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="e30f0-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="e30f0-365">**DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="e30f0-366">**DETECTIE VAN URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="e30f0-366">**URL detonation detection**</span></span>
- <span data-ttu-id="e30f0-367">**Gefilterde antispam**</span><span class="sxs-lookup"><span data-stu-id="e30f0-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="e30f0-368">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="e30f0-368">**ZAP removed**</span></span>
- <span data-ttu-id="e30f0-369">**Detectie door veilige koppelingen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="e30f0-370">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="e30f0-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e30f0-371">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="e30f0-371">**Export**:</span></span>

<span data-ttu-id="e30f0-372">Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="e30f0-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="e30f0-373">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e30f0-374">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e30f0-375">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e30f0-376">Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="e30f0-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e30f0-377">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e30f0-378">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e30f0-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e30f0-379">Technische weergave in het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="e30f0-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e30f0-380">E-mailrapport verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="e30f0-380">Sent and received email report</span></span>

<span data-ttu-id="e30f0-381">Het **rapport Verzonden** en ontvangen e-mail is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spamdetecties, malware en e-mail die als 'goed' zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="e30f0-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="e30f0-382">Het verschil tussen dit rapport en het [mailflowstatusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging. Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als één bericht tellen.</span><span class="sxs-lookup"><span data-stu-id="e30f0-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="e30f0-383">Met de statistische weergave en de detailweergave van het rapport kunt u 90 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="e30f0-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="e30f0-384">Als u het rapport wilt bekijken, opent u  het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en **selecteert u Verzonden en ontvangen e-mail.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="e30f0-385">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![E-mailwidget verzonden en ontvangen in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e30f0-387">Rapportweergave voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="e30f0-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="e30f0-388">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="e30f0-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e30f0-389">**Afbreken op: Type:** De grafiek bevat alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="e30f0-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="e30f0-390">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-390">**Total**</span></span>
  - <span data-ttu-id="e30f0-391">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-391">**Good mail**</span></span>
  - <span data-ttu-id="e30f0-392">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e30f0-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="e30f0-393">**Spamdetecties**</span><span class="sxs-lookup"><span data-stu-id="e30f0-393">**Spam detections**</span></span>
  - <span data-ttu-id="e30f0-394">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="e30f0-394">**Rule messages**</span></span>
  - <span data-ttu-id="e30f0-395">**Geavanceerde malware** (Microsoft Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="e30f0-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="e30f0-396">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, ziet u details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="e30f0-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Weergave typen in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="e30f0-398">**Af te breken op: Richting:** In de grafiek **worden totaal-,** **inkomende** en **uitgaande gegevens** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e30f0-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="e30f0-399">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, ziet u details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="e30f0-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtingsweergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="e30f0-401">**Inzoomen op** \> **Malware (anti-malware)**: Met deze selectie gaat u naar de detecties van [malware in het e-mailrapport.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="e30f0-402">**Inzoomen op** \> **Spamdetecties)**: Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e30f0-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e30f0-403">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e30f0-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e30f0-404">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="e30f0-405">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-405">Direction values</span></span>
- <span data-ttu-id="e30f0-406">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="e30f0-406">Type values</span></span>

<span data-ttu-id="e30f0-407">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e30f0-408">Tabelweergave Details voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="e30f0-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="e30f0-409">Als u in **de tabel Details weergeven** klikt **op:** Richting of Afbreken **door:** Richtingsweergave, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e30f0-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="e30f0-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-410">**Date (UTC)**</span></span>
- <span data-ttu-id="e30f0-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="e30f0-411">**Type**</span></span>
- <span data-ttu-id="e30f0-412">**Richting**</span><span class="sxs-lookup"><span data-stu-id="e30f0-412">**Direction**</span></span>
- <span data-ttu-id="e30f0-413">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="e30f0-413">**Message count**</span></span>

<span data-ttu-id="e30f0-414">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="e30f0-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e30f0-415">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="e30f0-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="e30f0-416">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="e30f0-416">Direction values</span></span>
- <span data-ttu-id="e30f0-417">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="e30f0-417">Type values</span></span>

<span data-ttu-id="e30f0-418">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e30f0-419">Rapport top afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="e30f0-419">Top senders and recipients report</span></span>

<span data-ttu-id="e30f0-420">Het **rapport Top senders and recipients** is a pie chart showing your top email senders and recipients.</span><span class="sxs-lookup"><span data-stu-id="e30f0-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="e30f0-421">Als u het rapport wilt bekijken, opent u  het [Beveiligingscentrum & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en selecteert u **Top senders and recipients**.</span><span class="sxs-lookup"><span data-stu-id="e30f0-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="e30f0-422">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="e30f0-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![De widget Top senders and recipients in the Reports dashboard](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e30f0-424">Rapportweergave voor het rapport Top senders and recipient report</span><span class="sxs-lookup"><span data-stu-id="e30f0-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="e30f0-425">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="e30f0-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e30f0-426">**Gegevens voor \> de belangrijkste afzenders van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="e30f0-427">**Gegevens voor \> de belangrijkste geadresseerden van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="e30f0-428">**Gegevens voor \> beste spamontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="e30f0-429">**Gegevens voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e30f0-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="e30f0-430">**Gegevens voor \> de beste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="e30f0-431">De samenstelling van het cirkeldiagram wordt gewijzigd op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="e30f0-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="e30f0-432">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u een aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="e30f0-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="e30f0-433">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport Belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e30f0-435">Tabelweergave Details voor het rapport Met de beste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="e30f0-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="e30f0-436">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="e30f0-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e30f0-437">**Gegevens voor \> de belangrijkste afzenders van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="e30f0-438">**Belangrijkste afzenders van e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-438">**Top mail senders**</span></span>
  - <span data-ttu-id="e30f0-439">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-439">**Count**</span></span>

- <span data-ttu-id="e30f0-440">**Gegevens voor \> de belangrijkste geadresseerden van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="e30f0-441">**Belangrijkste geadresseerden van e-mail**</span><span class="sxs-lookup"><span data-stu-id="e30f0-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="e30f0-442">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-442">**Count**</span></span>

- <span data-ttu-id="e30f0-443">**Gegevens voor \> beste spamontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="e30f0-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="e30f0-444">**Belangrijkste geadresseerden van spam**</span><span class="sxs-lookup"><span data-stu-id="e30f0-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="e30f0-445">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-445">**Count**</span></span>

- <span data-ttu-id="e30f0-446">**Gegevens voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e30f0-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="e30f0-447">**Belangrijkste ontvangers van malware**</span><span class="sxs-lookup"><span data-stu-id="e30f0-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="e30f0-448">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-448">**Count**</span></span>

- <span data-ttu-id="e30f0-449">**Gegevens voor \> de beste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="e30f0-450">**Belangrijkste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e30f0-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="e30f0-451">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="e30f0-451">**Count**</span></span>

<span data-ttu-id="e30f0-452">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e30f0-453">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="e30f0-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e30f0-454">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="e30f0-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e30f0-455">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in het Compliancecentrum & Beveiliging:</span><span class="sxs-lookup"><span data-stu-id="e30f0-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e30f0-456">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="e30f0-456">**Organization Management**</span></span>
- <span data-ttu-id="e30f0-457">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="e30f0-457">**Security Administrator**</span></span>
- <span data-ttu-id="e30f0-458">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="e30f0-458">**Security Reader**</span></span>
- <span data-ttu-id="e30f0-459">**Algemene lezer**</span><span class="sxs-lookup"><span data-stu-id="e30f0-459">**Global Reader**</span></span>

<span data-ttu-id="e30f0-460">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e30f0-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e30f0-461">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e30f0-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e30f0-462">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e30f0-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e30f0-463">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e30f0-463">Related topics</span></span>

[<span data-ttu-id="e30f0-464">Slimme rapporten en inzichten in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="e30f0-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e30f0-465">Inzichten in e-mailstroom in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="e30f0-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="e30f0-466">E-mailbeveiligingsrapporten weergeven in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="e30f0-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e30f0-467">Rapporten weergeven voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e30f0-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
