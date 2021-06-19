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
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029449"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="f9512-103">E-mailstroomrapporten weergeven in het dashboard Rapporten in & Compliance center</span><span class="sxs-lookup"><span data-stu-id="f9512-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9512-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f9512-104">**Applies to**</span></span>
- [<span data-ttu-id="f9512-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9512-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9512-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f9512-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f9512-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9512-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f9512-108">De meeste rapporten die in dit onderwerp worden beschreven, zijn beschikbaar in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="f9512-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f9512-109">Zie E-mailstroomrapporten [in het nieuwe Exchange-beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9512-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="f9512-110">Het [rapport Exchange-transportregel](view-email-security-reports.md#exchange-transport-rule-report) is beschikbaar in de Microsoft 365 Defender-portal.</span><span class="sxs-lookup"><span data-stu-id="f9512-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="f9512-111">Naast de e-mailstroomrapporten die [](mail-flow-insights-v2.md) beschikbaar zijn in het e-mailstroomdashboard in het beveiligings- & compliancecentrum, zijn er diverse extra e-mailstroomrapporten beschikbaar in het dashboard Rapporten om u te helpen uw Microsoft 365-organisatie te controleren.</span><span class="sxs-lookup"><span data-stu-id="f9512-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="f9512-112">Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het Beveiligings- & [compliancecentrum](https://protection.office.com) door naar **Rapportendashboard te** \> **gaan.**</span><span class="sxs-lookup"><span data-stu-id="f9512-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="f9512-113">Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="f9512-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Rapportendashboard in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="f9512-115">Connectorrapport</span><span class="sxs-lookup"><span data-stu-id="f9512-115">Connector report</span></span>

<span data-ttu-id="f9512-116">Het **rapport Connector toont** e-mailstroomactiviteit op de binnenkomende en uitgaande [verbindingslijnen](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9512-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="f9512-117">Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en selecteert u **Connector-rapport.**</span><span class="sxs-lookup"><span data-stu-id="f9512-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="f9512-118">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="f9512-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorrapportwidget in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="f9512-120">Rapportweergave voor het connectorrapport</span><span class="sxs-lookup"><span data-stu-id="f9512-120">Report view for the Connector report</span></span>

<span data-ttu-id="f9512-121">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="f9512-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9512-122">**Gegevens weergeven op: E-mailstroom:** In deze grafiek ziet u het aantal binnenkomende en uitgaande berichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="f9512-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="f9512-123">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="f9512-123">**Total**</span></span>
  - <span data-ttu-id="f9512-124">**Van internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="f9512-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9512-125">**Naar internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="f9512-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9512-126">Een specifieke verbindingslijn die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="f9512-127">Als u de gegevens in de grafiek wilt isoleren, gebruikt u gegevens **voor** besturingselementen tonen om een van deze opties of **Alle e-mailstroom te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="f9512-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens per e-mailstroom weergeven in het connectorrapport](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="f9512-129">**Gegevens weergeven op: TLS-gebruik:** In deze grafiek wordt het percentage TLS-versiegebruik (Transport Layer Security) voor e-mailstroom weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f9512-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="f9512-130">Als u de gegevens in de grafiek wilt isoleren, gebruikt u de optie Gegevens **voor besturingselementen** tonen om een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="f9512-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="f9512-131">**Alle e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="f9512-131">**All mail flow**</span></span>
  - <span data-ttu-id="f9512-132">**Van internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="f9512-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="f9512-133">**Naar internet zonder verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="f9512-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="f9512-134">Een specifieke verbindingslijn die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-134">A specific connector that you've configured.</span></span>

  ![Gegevens weergeven op TLS-gebruik in het connectorrapport](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="f9512-136">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="f9512-137">Detailtabelweergave voor het connectorrapport</span><span class="sxs-lookup"><span data-stu-id="f9512-137">Details table view for the Connector report</span></span>

<span data-ttu-id="f9512-138">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f9512-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9512-139">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-139">**Date**</span></span>
- <span data-ttu-id="f9512-140">**Richting en naam van verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="f9512-140">**Connector direction and name**</span></span>
- <span data-ttu-id="f9512-141">**Connectortype**</span><span class="sxs-lookup"><span data-stu-id="f9512-141">**Connector type**</span></span>
- <span data-ttu-id="f9512-142">**Gedwongen TLS?**: De waarde **Waar** of **Onwaar**.</span><span class="sxs-lookup"><span data-stu-id="f9512-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="f9512-143">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="f9512-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="f9512-144">**TLS 1,0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="f9512-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="f9512-145">**TLS 1,1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="f9512-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="f9512-146">**TLS 1,2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="f9512-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="f9512-147">**Volume:** Het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="f9512-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="f9512-148">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9512-149">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="f9512-150">Rapport met exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="f9512-150">Exchange transport rule report</span></span>

<span data-ttu-id="f9512-151">Het **rapport Exchange-transportregel toont** het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9512-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="f9512-152">Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en **selecteert u Exchange Transport-regel**.</span><span class="sxs-lookup"><span data-stu-id="f9512-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="f9512-153">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="f9512-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-transportregelwidget in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9512-155">Rapportweergave voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="f9512-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9512-156">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="f9512-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="f9512-157">**Gegevens weergeven op: Exchange-transportregels** \> **Afbreed door: Richting:** In deze grafiek  ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door transportregels.</span><span class="sxs-lookup"><span data-stu-id="f9512-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="f9512-158">**Gegevens weergeven op: Exchange-transportregels** \> **Afbreed door: Ernst:** In deze  grafiek ziet u het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een **lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="f9512-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="f9512-159">U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="f9512-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="f9512-160">Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="f9512-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="f9512-161">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Afbreiding door: Richting:** In deze  grafiek ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door DLP-transportregels (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="f9512-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="f9512-162">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="f9512-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9512-163">**Gegevens voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="f9512-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9512-164">**Gegevens voor: Gecompromitteerd gebruikers**</span><span class="sxs-lookup"><span data-stu-id="f9512-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9512-165">**Gegevens voor: Laag volume aan gedetecteerde Amerikaanse Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9512-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="f9512-166">**Gegevens weergeven op: DLP Exchange-transportregels** \> **Afbreiding door: Richting:** In  deze weergave ziet u  het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een lage ernst die zijn beïnvloed door DLP-transportregels.</span><span class="sxs-lookup"><span data-stu-id="f9512-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="f9512-167">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="f9512-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="f9512-168">**Gegevens voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="f9512-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="f9512-169">**Gegevens voor: Gecompromitteerd gebruikers**</span><span class="sxs-lookup"><span data-stu-id="f9512-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="f9512-170">**Gegevens voor: Laag volume aan gedetecteerde Amerikaanse Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="f9512-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="f9512-171">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters::</span><span class="sxs-lookup"><span data-stu-id="f9512-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="f9512-172">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="f9512-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9512-173">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-173">Direction values</span></span>
- <span data-ttu-id="f9512-174">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-174">Severity values</span></span>

![Rapportweergave in het rapport Exchange-transportregel](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="f9512-176">Tabelweergave Details voor het rapport Exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="f9512-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="f9512-177">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="f9512-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9512-178">**Gegevens weergeven door: Exchange-transportregels:**</span><span class="sxs-lookup"><span data-stu-id="f9512-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="f9512-179">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-179">**Date**</span></span>
  - <span data-ttu-id="f9512-180">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f9512-180">**Transport rule**</span></span>
  - <span data-ttu-id="f9512-181">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="f9512-181">**Subject**</span></span>
  - <span data-ttu-id="f9512-182">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="f9512-182">**Sender address**</span></span>
  - <span data-ttu-id="f9512-183">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="f9512-183">**Recipient address**</span></span>
  - <span data-ttu-id="f9512-184">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="f9512-184">**Severity**</span></span>
  - <span data-ttu-id="f9512-185">**Richting**</span><span class="sxs-lookup"><span data-stu-id="f9512-185">**Direction**</span></span>

- <span data-ttu-id="f9512-186">**Gegevens weergeven op: DLP Exchange-transportregels**:</span><span class="sxs-lookup"><span data-stu-id="f9512-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="f9512-187">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-187">**Date**</span></span>
  - <span data-ttu-id="f9512-188">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="f9512-188">**DLP policy**</span></span>
  - <span data-ttu-id="f9512-189">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f9512-189">**Transport rule**</span></span>
  - <span data-ttu-id="f9512-190">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="f9512-190">**Subject**</span></span>
  - <span data-ttu-id="f9512-191">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="f9512-191">**Sender address**</span></span>
  - <span data-ttu-id="f9512-192">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="f9512-192">**Recipient address**</span></span>
  - <span data-ttu-id="f9512-193">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="f9512-193">**Severity**</span></span>
  - <span data-ttu-id="f9512-194">**Richting**</span><span class="sxs-lookup"><span data-stu-id="f9512-194">**Direction**</span></span>

<span data-ttu-id="f9512-195">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="f9512-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9512-196">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="f9512-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9512-197">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-197">Direction values</span></span>
- <span data-ttu-id="f9512-198">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-198">Severity values</span></span>

<span data-ttu-id="f9512-199">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="f9512-200">Doorsturen van rapport</span><span class="sxs-lookup"><span data-stu-id="f9512-200">Forwarding report</span></span>

<span data-ttu-id="f9512-201">In **het rapport Doorsturen** ziet u de automatisch doorgestuurde berichten van uw organisatie naar externe domeinen vanuit Exchange Online postvakken.</span><span class="sxs-lookup"><span data-stu-id="f9512-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="f9512-202">Doorgestuurde berichten kunnen een beveiligings- of compliancerisico opleveren en kunnen een gekromd account aangeven.</span><span class="sxs-lookup"><span data-stu-id="f9512-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="f9512-203">Als u het rapport wilt bekijken, opent u  het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en selecteert u **Rapport doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="f9512-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="f9512-204">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="f9512-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Rapportwidget doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="f9512-206">Rapportweergave voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="f9512-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="f9512-207">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="f9512-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9512-208">**Gegevens voor: Doorsturen methoden**: De volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f9512-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="f9512-209">**Transportregel:** ook wel [e-mailstroomregels genoemd.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="f9512-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="f9512-210">**Postvakregel:** Ook wel regels [voor Postvak IN genoemd.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="f9512-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![De weergave Doorsturen van methoden in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="f9512-212">**Gegevens weergeven voor: Domeinen doorsturen:** in deze weergave ziet u de geadresseerdedomeinen die de bestemmingen zijn voor doorsturen.</span><span class="sxs-lookup"><span data-stu-id="f9512-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![De weergave Domeinen doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="f9512-214">**Gegevens voor: Doorsturen:** De volgende doorsturen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f9512-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="f9512-215">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="f9512-215">**Transport rule**</span></span>
  - <span data-ttu-id="f9512-216">Het postvak met de regel Postvak IN doorsturen.</span><span class="sxs-lookup"><span data-stu-id="f9512-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![De weergave Doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="f9512-218">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="f9512-219">Tabelweergave Details voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="f9512-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="f9512-220">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f9512-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="f9512-221">**Doorst:De** waarde **Transportregel** of het postvak met de regel Postvak IN doorsturen.</span><span class="sxs-lookup"><span data-stu-id="f9512-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="f9512-222">**Doorsturen:** De waarde **Regel Postvak** of **Transportregel**.</span><span class="sxs-lookup"><span data-stu-id="f9512-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="f9512-223">**Naam van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="f9512-223">**Recipient name**</span></span>
- <span data-ttu-id="f9512-224">**Domein geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="f9512-224">**Recipient domain**</span></span>
- <span data-ttu-id="f9512-225">**Details:** dit is de GUID-waarde van de e-mailstroomregel of de waarde RuleIdentity van de regel Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="f9512-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="f9512-226">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-226">**Count**</span></span>
- <span data-ttu-id="f9512-227">**Eerste doorgestuurde datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-227">**First forward date**</span></span>

<span data-ttu-id="f9512-228">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9512-229">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="f9512-230">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="f9512-230">Mailflow status report</span></span>

<span data-ttu-id="f9512-231">Het **rapport Mailflow-status** is vergelijkbaar met het e-mailrapport Verzonden en [ontvangen,](#sent-and-received-email-report)met aanvullende informatie over e-mail die aan de rand is toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="f9512-232">Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat deze wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f9512-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f9512-233">Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="f9512-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="f9512-234">Als u het rapport wilt bekijken, opent u  het [beveiligingscentrum & compliancecentrum,](https://protection.office.com)gaat u naar Het dashboard Rapporten en selecteert u \>  **Mailflow-statusrapport.**</span><span class="sxs-lookup"><span data-stu-id="f9512-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="f9512-235">Als u rechtstreeks naar het rapport **E-mailstroomstatus wilt gaan,** opent <https://protection.office.com/mailflowStatusReport> u .</span><span class="sxs-lookup"><span data-stu-id="f9512-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Rapportwidget Mailflow-status in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9512-237">Typweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="f9512-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="f9512-238">Wanneer u het rapport opent, is **het tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="f9512-239">Standaard bevat deze weergave een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="f9512-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9512-240">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="f9512-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="f9512-241">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="f9512-241">**Direction**:</span></span>

  - <span data-ttu-id="f9512-242">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="f9512-242">**Inbound**</span></span>
  - <span data-ttu-id="f9512-243">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="f9512-243">**Outbound**</span></span>
  - <span data-ttu-id="f9512-244">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="f9512-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f9512-245">afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="f9512-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="f9512-246">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="f9512-246">**Type**:</span></span>

  - <span data-ttu-id="f9512-247">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-247">**Good mail**</span></span>
  - <span data-ttu-id="f9512-248">**Malware**</span><span class="sxs-lookup"><span data-stu-id="f9512-248">**Malware**</span></span>
  - <span data-ttu-id="f9512-249">**Spam**</span><span class="sxs-lookup"><span data-stu-id="f9512-249">**Spam**</span></span>
  - <span data-ttu-id="f9512-250">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="f9512-250">**Edge protection**</span></span>
  - <span data-ttu-id="f9512-251">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="f9512-251">**Rule messages**</span></span>
  - <span data-ttu-id="f9512-252">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-252">**Phishing email**</span></span>

<span data-ttu-id="f9512-253">De grafiek wordt ingedeeld op basis van **de waarden Type.**</span><span class="sxs-lookup"><span data-stu-id="f9512-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="f9512-254">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="f9512-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="f9512-255">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="f9512-255">The data table contains the following information:</span></span>

- <span data-ttu-id="f9512-256">**Richting**</span><span class="sxs-lookup"><span data-stu-id="f9512-256">**Direction**</span></span>
- <span data-ttu-id="f9512-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9512-257">**Type**</span></span>
- <span data-ttu-id="f9512-258">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="f9512-258">**24 hours**</span></span>
- <span data-ttu-id="f9512-259">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="f9512-259">**3 days**</span></span>
- <span data-ttu-id="f9512-260">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="f9512-260">**7 days**</span></span>
- <span data-ttu-id="f9512-261">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="f9512-261">**15 days**</span></span>
- <span data-ttu-id="f9512-262">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="f9512-262">**30 days**</span></span>

<span data-ttu-id="f9512-263">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f9512-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="f9512-264">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9512-265">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="f9512-266">**Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="f9512-267">**Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9512-268">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="f9512-268">**Export**:</span></span>

<span data-ttu-id="f9512-269">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9512-270">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f9512-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9512-271">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="f9512-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9512-272">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f9512-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Weergave typen in het rapport Mailflow-status](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9512-274">Richtingsweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="f9512-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="f9512-275">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f9512-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9512-276">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="f9512-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="f9512-277">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="f9512-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="f9512-278">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f9512-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="f9512-279">De gegevenstabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="f9512-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="f9512-280">De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.</span><span class="sxs-lookup"><span data-stu-id="f9512-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="f9512-281">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="f9512-281">**Export**:</span></span>

<span data-ttu-id="f9512-282">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="f9512-283">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="f9512-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="f9512-284">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="f9512-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9512-285">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f9512-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtingsweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9512-287">Trechterweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="f9512-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="f9512-288">In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="f9512-289">Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="f9512-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="f9512-290">Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="f9512-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9512-291">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="f9512-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f9512-292">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="f9512-292">**Direction**:</span></span>

  - <span data-ttu-id="f9512-293">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="f9512-293">**Inbound**</span></span>
  - <span data-ttu-id="f9512-294">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="f9512-294">**Outbound**</span></span>
  - <span data-ttu-id="f9512-295">**Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).</span><span class="sxs-lookup"><span data-stu-id="f9512-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="f9512-296">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="f9512-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9512-297">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f9512-298">In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="f9512-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="f9512-299">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-299">**Total email**</span></span>
- <span data-ttu-id="f9512-300">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="f9512-300">**Email after edge protection**</span></span>
- <span data-ttu-id="f9512-301">**E-mail na anti-malware, bestandsreputatie, bestandstypeblok**</span><span class="sxs-lookup"><span data-stu-id="f9512-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="f9512-302">**E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="f9512-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="f9512-303">**E-mail na antispam, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="f9512-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="f9512-304">**E-mail na gebruikers- en domein-imitatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9512-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="f9512-305">**E-mail na bestand en URL-detonatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9512-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="f9512-306">**E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="f9512-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="f9512-307"><sup>1</sup> Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="f9512-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="f9512-308">Als u het e-mailbericht wilt weergeven dat is gefilterd op EOP of Defender Office 365 afzonderlijk, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="f9512-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="f9512-309">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="f9512-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f9512-310">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-310">**Date**</span></span>
- <span data-ttu-id="f9512-311">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-311">**Total email**</span></span>
- <span data-ttu-id="f9512-312">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="f9512-312">**Edge protection**</span></span>
- <span data-ttu-id="f9512-313">**Anti-malware, bestandsreputatie, bestandstypeblok:**</span><span class="sxs-lookup"><span data-stu-id="f9512-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="f9512-314">**Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="f9512-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="f9512-315">**Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="f9512-316">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="f9512-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="f9512-317">**URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="f9512-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="f9512-318">**Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.</span><span class="sxs-lookup"><span data-stu-id="f9512-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="f9512-319">**Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.</span><span class="sxs-lookup"><span data-stu-id="f9512-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="f9512-320">**Antispam, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="f9512-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="f9512-321">**Bulkmailfilters:** Berichten die zijn gefilterd als gevolg van een poging om bulkmail bij de geadresseerden te bezorgen.</span><span class="sxs-lookup"><span data-stu-id="f9512-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="f9512-322">**Gebruikers- en domein-imitatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f9512-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f9512-323">**Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="f9512-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="f9512-324">**Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="f9512-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="f9512-325">**Bestands- en URL-detonatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="f9512-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="f9512-326">**Bestandsdetonatie:** Berichten gefilterd op een Safe bijlagenbeleid.</span><span class="sxs-lookup"><span data-stu-id="f9512-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="f9512-327">**URL-detonatie:** bericht gefilterd door een Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="f9512-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="f9512-328">**Beveiliging na aflevering en ZAP (ATP) of ZAP (EOP)**: ZAP geeft automatisch nul uur aan.</span><span class="sxs-lookup"><span data-stu-id="f9512-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="f9512-329">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="f9512-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f9512-330">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="f9512-330">**Export**:</span></span>

<span data-ttu-id="f9512-331">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="f9512-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="f9512-332">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="f9512-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f9512-333">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="f9512-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f9512-334">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="f9512-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f9512-335">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="f9512-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f9512-336">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="f9512-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9512-337">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f9512-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Trechterweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="f9512-339">Technische weergave voor het mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="f9512-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="f9512-340">De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f9512-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="f9512-341">In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f9512-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="f9512-342">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="f9512-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="f9512-343">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="f9512-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="f9512-344">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="f9512-344">**Direction**:</span></span>

  - <span data-ttu-id="f9512-345">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="f9512-345">**Inbound**</span></span>
  - <span data-ttu-id="f9512-346">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="f9512-346">**Outbound**</span></span>
  - <span data-ttu-id="f9512-347">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="f9512-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="f9512-348">afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)</span><span class="sxs-lookup"><span data-stu-id="f9512-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="f9512-349">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="f9512-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9512-350">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="f9512-351">In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="f9512-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f9512-352">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-352">**Total email**</span></span>
- <span data-ttu-id="f9512-353">**Rand toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="f9512-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="f9512-354">**Geen malware,** **Safe detectie van bijlagen,** detectie van <sup>\*</sup> **anti-malwareprogramma's** en **regelberichten**</span><span class="sxs-lookup"><span data-stu-id="f9512-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="f9512-355">**Geen phish,** **DMARC-fout,** **imitatiedetectie,** **spoofdetectie** en **Phish-detectie**</span><span class="sxs-lookup"><span data-stu-id="f9512-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="f9512-356">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f9512-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="f9512-357">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="f9512-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="f9512-358">**Niet-schadelijke e-mail,** **Safe koppelingendetectie** <sup>\*</sup> en **ZAP**</span><span class="sxs-lookup"><span data-stu-id="f9512-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="f9512-359"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f9512-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="f9512-360">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.</span><span class="sxs-lookup"><span data-stu-id="f9512-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="f9512-361">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="f9512-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="f9512-362">**Datum**</span><span class="sxs-lookup"><span data-stu-id="f9512-362">**Date**</span></span>
- <span data-ttu-id="f9512-363">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-363">**Total email**</span></span>
- <span data-ttu-id="f9512-364">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="f9512-364">**Edge filtered**</span></span>
- <span data-ttu-id="f9512-365">**Anti-malware engine, Safe Bijlagen, regel gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="f9512-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="f9512-366">**Regel gefilterd:** Berichten gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="f9512-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="f9512-367">**DMARC, imitatie, spoof, phish gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="f9512-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="f9512-368">**DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="f9512-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="f9512-369">**DETECTIE VAN URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="f9512-369">**URL detonation detection**</span></span>
- <span data-ttu-id="f9512-370">**Gefilterde antispam**</span><span class="sxs-lookup"><span data-stu-id="f9512-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="f9512-371">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="f9512-371">**ZAP removed**</span></span>
- <span data-ttu-id="f9512-372">**Detectie door Safe koppelingen**</span><span class="sxs-lookup"><span data-stu-id="f9512-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="f9512-373">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="f9512-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="f9512-374">**Exporteren**:</span><span class="sxs-lookup"><span data-stu-id="f9512-374">**Export**:</span></span>

<span data-ttu-id="f9512-375">Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="f9512-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="f9512-376">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="f9512-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="f9512-377">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="f9512-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="f9512-378">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="f9512-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="f9512-379">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="f9512-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="f9512-380">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="f9512-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="f9512-381">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f9512-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Technische weergave in het rapport Mailflow-status](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="f9512-383">E-mailrapport verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="f9512-383">Sent and received email report</span></span>

<span data-ttu-id="f9512-384">Het **rapport Verzonden** en ontvangen e-mail is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spamdetecties, malware en e-mail die als 'goed' zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="f9512-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="f9512-385">Het verschil tussen dit rapport en het [mailflowstatusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f9512-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="f9512-386">**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als één bericht tellen.</span><span class="sxs-lookup"><span data-stu-id="f9512-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="f9512-387">Met de statistische weergave en de detailweergave van het rapport kunt u 90 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="f9512-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="f9512-388">Als u het rapport wilt bekijken, opent u  het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en **selecteert u Verzonden en ontvangen e-mail.**</span><span class="sxs-lookup"><span data-stu-id="f9512-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="f9512-389">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="f9512-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![E-mailwidget verzonden en ontvangen in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9512-391">Rapportweergave voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="f9512-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="f9512-392">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="f9512-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9512-393">**Afbreken op: Type:** De grafiek bevat alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="f9512-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="f9512-394">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="f9512-394">**Total**</span></span>
  - <span data-ttu-id="f9512-395">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-395">**Good mail**</span></span>
  - <span data-ttu-id="f9512-396">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9512-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="f9512-397">**Spamdetecties**</span><span class="sxs-lookup"><span data-stu-id="f9512-397">**Spam detections**</span></span>
  - <span data-ttu-id="f9512-398">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="f9512-398">**Rule messages**</span></span>
  - <span data-ttu-id="f9512-399">**Geavanceerde malware** (Microsoft Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="f9512-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="f9512-400">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, ziet u details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="f9512-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Weergave typen in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="f9512-402">**Af te breken op: Richting:** In de grafiek **worden totaal-,** **inkomende** en **uitgaande gegevens** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f9512-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="f9512-403">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, ziet u details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="f9512-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtingsweergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="f9512-405">**Inzoomen op** \> **Malware (anti-malware)**: Met deze selectie gaat u naar het [rapport Malwaredetecties.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="f9512-406">**Inzoomen op** \> **Spamdetecties)**: Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f9512-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="f9512-407">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="f9512-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9512-408">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="f9512-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9512-409">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-409">Direction values</span></span>
- <span data-ttu-id="f9512-410">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="f9512-410">Type values</span></span>

<span data-ttu-id="f9512-411">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="f9512-412">Tabelweergave Details voor het e-mailrapport Verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="f9512-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="f9512-413">Als u in **de tabel Details weergeven** klikt **op:** Richting of Afbreken **door:** Richtingsweergave, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f9512-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="f9512-414">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f9512-414">**Date (UTC)**</span></span>
- <span data-ttu-id="f9512-415">**Type**</span><span class="sxs-lookup"><span data-stu-id="f9512-415">**Type**</span></span>
- <span data-ttu-id="f9512-416">**Richting**</span><span class="sxs-lookup"><span data-stu-id="f9512-416">**Direction**</span></span>
- <span data-ttu-id="f9512-417">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="f9512-417">**Message count**</span></span>

<span data-ttu-id="f9512-418">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="f9512-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f9512-419">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="f9512-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="f9512-420">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="f9512-420">Direction values</span></span>
- <span data-ttu-id="f9512-421">Waarden typen</span><span class="sxs-lookup"><span data-stu-id="f9512-421">Type values</span></span>

<span data-ttu-id="f9512-422">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="f9512-423">Rapport top afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="f9512-423">Top senders and recipients report</span></span>

<span data-ttu-id="f9512-424">Het **rapport Top senders and recipients** is a pie chart showing your top email senders and recipients.</span><span class="sxs-lookup"><span data-stu-id="f9512-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="f9512-425">Als u het rapport wilt bekijken, opent u  het [Beveiligingscentrum & Compliancecentrum,](https://protection.office.com)gaat u naar \> **Rapportendashboard** en selecteert u **Top senders and recipients**.</span><span class="sxs-lookup"><span data-stu-id="f9512-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="f9512-426">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="f9512-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![De widget Top senders and recipients in the Reports dashboard](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9512-428">Rapportweergave voor het rapport Top senders and recipient report</span><span class="sxs-lookup"><span data-stu-id="f9512-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9512-429">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="f9512-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f9512-430">**Gegevens voor \> de belangrijkste afzenders van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="f9512-431">**Gegevens voor \> de belangrijkste geadresseerden van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="f9512-432">**Gegevens voor \> beste spamontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="f9512-433">**Gegevens voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9512-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="f9512-434">**Gegevens voor \> de beste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f9512-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="f9512-435">De samenstelling van het cirkeldiagram wordt gewijzigd op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="f9512-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="f9512-436">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u een aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="f9512-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="f9512-437">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport Belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="f9512-439">Tabelweergave Details voor het rapport Met de beste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="f9512-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="f9512-440">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="f9512-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f9512-441">**Gegevens voor \> de belangrijkste afzenders van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="f9512-442">**Belangrijkste afzenders van e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-442">**Top mail senders**</span></span>
  - <span data-ttu-id="f9512-443">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-443">**Count**</span></span>

- <span data-ttu-id="f9512-444">**Gegevens voor \> de belangrijkste geadresseerden van e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="f9512-445">**Belangrijkste geadresseerden van e-mail**</span><span class="sxs-lookup"><span data-stu-id="f9512-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="f9512-446">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-446">**Count**</span></span>

- <span data-ttu-id="f9512-447">**Gegevens voor \> beste spamontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="f9512-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="f9512-448">**Belangrijkste geadresseerden van spam**</span><span class="sxs-lookup"><span data-stu-id="f9512-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="f9512-449">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-449">**Count**</span></span>

- <span data-ttu-id="f9512-450">**Gegevens voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="f9512-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="f9512-451">**Belangrijkste ontvangers van malware**</span><span class="sxs-lookup"><span data-stu-id="f9512-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="f9512-452">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-452">**Count**</span></span>

- <span data-ttu-id="f9512-453">**Gegevens voor \> de beste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f9512-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="f9512-454">**Belangrijkste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f9512-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="f9512-455">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="f9512-455">**Count**</span></span>

<span data-ttu-id="f9512-456">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="f9512-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f9512-457">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="f9512-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="f9512-458">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="f9512-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="f9512-459">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in het Compliancecentrum & Beveiliging:</span><span class="sxs-lookup"><span data-stu-id="f9512-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f9512-460">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="f9512-460">**Organization Management**</span></span>
- <span data-ttu-id="f9512-461">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="f9512-461">**Security Administrator**</span></span>
- <span data-ttu-id="f9512-462">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="f9512-462">**Security Reader**</span></span>
- <span data-ttu-id="f9512-463">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="f9512-463">**Global Reader**</span></span>

<span data-ttu-id="f9512-464">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9512-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9512-465">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9512-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f9512-466">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f9512-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9512-467">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f9512-467">Related topics</span></span>

[<span data-ttu-id="f9512-468">Slimme rapporten en inzichten in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="f9512-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f9512-469">Inzichten in e-mailstroom in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="f9512-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="f9512-470">E-mailbeveiligingsrapporten weergeven in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="f9512-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f9512-471">Rapporten weergeven voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f9512-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
