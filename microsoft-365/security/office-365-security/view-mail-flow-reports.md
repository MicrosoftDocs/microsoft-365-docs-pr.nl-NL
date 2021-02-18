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
description: Beheerders kunnen meer informatie krijgen over de e-mailstroomrapporten die beschikbaar zijn in het dashboard Rapporten in het & Compliancecentrum.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286715"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="2ed78-103">E-mailstroomrapporten weergeven in het dashboard Rapporten in & Compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="2ed78-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2ed78-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2ed78-104">**Applies to**</span></span>
- [<span data-ttu-id="2ed78-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2ed78-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2ed78-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2ed78-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2ed78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ed78-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2ed78-108">Naast de e-mailstroomrapporten die beschikbaar zijn in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het beveiligings- & Compliancecentrum, vindt u diverse aanvullende e-mailstroomrapporten in het dashboard Rapporten om u te helpen uw Microsoft 365-organisatie te bewaken.</span><span class="sxs-lookup"><span data-stu-id="2ed78-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="2ed78-109">Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het beveiligings- [& compliancecentrum](https://protection.office.com) door naar het dashboard Rapporten **te** \> **gaan.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="2ed78-110">Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard Rapporten in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="2ed78-112">Connectorrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-112">Connector report</span></span>

<span data-ttu-id="2ed78-113">Het **rapport Connector toont** de activiteit van de e-mailstroom op de binnenkomende en uitgaande [connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2ed78-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="2ed78-114">Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en **selecteert u het rapport Connector.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="2ed78-115">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Connectorrapportwidget in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="2ed78-117">Rapportweergave voor het rapport Connector</span><span class="sxs-lookup"><span data-stu-id="2ed78-117">Report view for the Connector report</span></span>

<span data-ttu-id="2ed78-118">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="2ed78-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="2ed78-119">**Gegevens weergeven op: E-mailstroom:** in deze grafiek ziet u het aantal inkomende en uitgaande berichten, ingedeeld in:</span><span class="sxs-lookup"><span data-stu-id="2ed78-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="2ed78-120">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-120">**Total**</span></span>
  - <span data-ttu-id="2ed78-121">**Van internet zonder een connector**</span><span class="sxs-lookup"><span data-stu-id="2ed78-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2ed78-122">**Naar internet zonder een connector**</span><span class="sxs-lookup"><span data-stu-id="2ed78-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2ed78-123">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="2ed78-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="2ed78-124">Als u de gegevens in  de grafiek wilt isoleren, gebruikt u Gegevens voor besturingselementen tonen om een van deze opties of **Alle e-mailstroom te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Gegevens weergeven per e-mailstroom in het rapport Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="2ed78-126">**Gegevens weergeven met: TLS-gebruik:** in deze grafiek ziet u het percentage versiegebruik van TLS (Transport Layer Security) voor de e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="2ed78-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="2ed78-127">Als u de gegevens in de grafiek wilt isoleren, gebruikt u gegevens voor **besturingselementen** om een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="2ed78-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="2ed78-128">**Alle e-mailstromen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-128">**All mail flow**</span></span>
  - <span data-ttu-id="2ed78-129">**Van internet zonder een connector**</span><span class="sxs-lookup"><span data-stu-id="2ed78-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="2ed78-130">**Naar internet zonder een connector**</span><span class="sxs-lookup"><span data-stu-id="2ed78-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="2ed78-131">Een specifieke connector die u hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="2ed78-131">A specific connector that you've configured.</span></span>

  ![Gegevens weergeven op TLS-gebruik in het rapport Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="2ed78-133">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="2ed78-134">Tabelweergave Details voor het rapport Connector</span><span class="sxs-lookup"><span data-stu-id="2ed78-134">Details table view for the Connector report</span></span>

<span data-ttu-id="2ed78-135">Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ed78-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2ed78-136">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-136">**Date**</span></span>
- <span data-ttu-id="2ed78-137">**Richting en naam van verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="2ed78-137">**Connector direction and name**</span></span>
- <span data-ttu-id="2ed78-138">**Type verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="2ed78-138">**Connector type**</span></span>
- <span data-ttu-id="2ed78-139">**Geforceerd TLS?**: De waarde **Waar** of **Onwaar.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="2ed78-140">**Geen TLS** (percentage)</span><span class="sxs-lookup"><span data-stu-id="2ed78-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="2ed78-141">**TLS 1.0** (percentage)</span><span class="sxs-lookup"><span data-stu-id="2ed78-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="2ed78-142">**TLS 1.1** (percentage)</span><span class="sxs-lookup"><span data-stu-id="2ed78-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="2ed78-143">**TLS 1.2** (percentage)</span><span class="sxs-lookup"><span data-stu-id="2ed78-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="2ed78-144">**Volume:** het aantal berichten.</span><span class="sxs-lookup"><span data-stu-id="2ed78-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="2ed78-145">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2ed78-146">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="2ed78-147">Exchange-transportregelrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-147">Exchange transport rule report</span></span>

<span data-ttu-id="2ed78-148">Het **Exchange-transportregelrapport** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2ed78-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="2ed78-149">Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en selecteert u de **Exchange-transportregel.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="2ed78-150">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange-transportregelwidget in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2ed78-152">Rapportweergave voor het Exchange-transportregelrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="2ed78-153">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="2ed78-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="2ed78-154">**Gegevens weergeven met: Exchange-transportregels** \> **Op te breken met: Richting:** in deze  grafiek ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door transportregels.</span><span class="sxs-lookup"><span data-stu-id="2ed78-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="2ed78-155">**Gegevens weergeven op: Exchange-transportregels** \> **Op te breken door: Ernst:** in  deze grafiek ziet u het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een **lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="2ed78-156">U stelt het niveau van ernst in als een actie in de regel (**Controleer** deze regel met ernstniveau of _SetAuditSeverity)._</span><span class="sxs-lookup"><span data-stu-id="2ed78-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="2ed78-157">Zie [E-mailstroomregelacties in Exchange Online voor meer informatie.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="2ed78-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="2ed78-158">**Gegevens weergeven met: DLP Exchange-transportregels** \> **Op te delen met: Richting:** in deze  grafiek ziet u het aantal **inkomende** en uitgaande berichten dat is beïnvloed door DLP-transportregels (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="2ed78-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="2ed78-159">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="2ed78-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2ed78-160">**Gegevens tonen voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="2ed78-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2ed78-161">**Gegevens tonen voor: gecompromitteerde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="2ed78-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2ed78-162">**Gegevens tonen voor: laag volume van gedetecteerde V.S. Act**</span><span class="sxs-lookup"><span data-stu-id="2ed78-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="2ed78-163">**Gegevens weergeven met: DLP Exchange-transportregels** \> **Op te breken met: Richting:** in deze weergave ziet u  het aantal berichten met hoge ernst en gemiddelde ernst en berichten met lage ernst die zijn beïnvloed door DLP-transportregels. </span><span class="sxs-lookup"><span data-stu-id="2ed78-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="2ed78-164">U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:</span><span class="sxs-lookup"><span data-stu-id="2ed78-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="2ed78-165">**Gegevens tonen voor: Alle DLP-transportregels**</span><span class="sxs-lookup"><span data-stu-id="2ed78-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="2ed78-166">**Gegevens tonen voor: gecompromitteerde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="2ed78-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="2ed78-167">**Gegevens tonen voor: laag volume van gedetecteerde V.S. Act**</span><span class="sxs-lookup"><span data-stu-id="2ed78-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="2ed78-168">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="2ed78-169">**Begindatum** **en einddatum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="2ed78-170">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-170">Direction values</span></span>
- <span data-ttu-id="2ed78-171">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-171">Severity values</span></span>

![Rapportweergave in het Exchange-transportregelrapport](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="2ed78-173">Detailtabelweergave voor het Exchange-transportregelrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="2ed78-174">Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="2ed78-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2ed78-175">**Gegevens weergeven op: Exchange-transportregels:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="2ed78-176">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-176">**Date**</span></span>
  - <span data-ttu-id="2ed78-177">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="2ed78-177">**Transport rule**</span></span>
  - <span data-ttu-id="2ed78-178">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="2ed78-178">**Subject**</span></span>
  - <span data-ttu-id="2ed78-179">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2ed78-179">**Sender address**</span></span>
  - <span data-ttu-id="2ed78-180">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="2ed78-180">**Recipient address**</span></span>
  - <span data-ttu-id="2ed78-181">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="2ed78-181">**Severity**</span></span>
  - <span data-ttu-id="2ed78-182">**Richting**</span><span class="sxs-lookup"><span data-stu-id="2ed78-182">**Direction**</span></span>

- <span data-ttu-id="2ed78-183">**Gegevens weergeven met: DLP Exchange-transportregels:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="2ed78-184">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-184">**Date**</span></span>
  - <span data-ttu-id="2ed78-185">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="2ed78-185">**DLP policy**</span></span>
  - <span data-ttu-id="2ed78-186">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="2ed78-186">**Transport rule**</span></span>
  - <span data-ttu-id="2ed78-187">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="2ed78-187">**Subject**</span></span>
  - <span data-ttu-id="2ed78-188">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="2ed78-188">**Sender address**</span></span>
  - <span data-ttu-id="2ed78-189">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="2ed78-189">**Recipient address**</span></span>
  - <span data-ttu-id="2ed78-190">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="2ed78-190">**Severity**</span></span>
  - <span data-ttu-id="2ed78-191">**Richting**</span><span class="sxs-lookup"><span data-stu-id="2ed78-191">**Direction**</span></span>

<span data-ttu-id="2ed78-192">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2ed78-193">**Begindatum** **en einddatum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="2ed78-194">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-194">Direction values</span></span>
- <span data-ttu-id="2ed78-195">Ernstwaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-195">Severity values</span></span>

<span data-ttu-id="2ed78-196">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="2ed78-197">Doorsturen-rapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-197">Forwarding report</span></span>

<span data-ttu-id="2ed78-198">In **het rapport Doorsturen** worden de automatisch doorgestuurde berichten van uw organisatie naar externe domeinen vanuit Exchange Online-postvakken doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="2ed78-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="2ed78-199">Doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen en kunnen een gekromd account aangeven.</span><span class="sxs-lookup"><span data-stu-id="2ed78-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="2ed78-200">Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en **selecteert u Rapport doorsturen.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="2ed78-201">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget Rapport doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="2ed78-203">Rapportweergave voor het doorsturende rapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="2ed78-204">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="2ed78-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2ed78-205">**Gegevens tonen voor: Methoden voor doorsturen:** de volgende methoden worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ed78-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="2ed78-206">**Transportregel:** ook wel [e-mailstroomregels genoemd.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="2ed78-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="2ed78-207">**Postvakregel:** ook wel regels [voor Postvak IN genoemd.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="2ed78-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Weergave doorsturenmethoden in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="2ed78-209">**Gegevens weergeven voor: Doorsturen-domeinen:** in deze weergave ziet u de geadresseerdedomeinen die de bestemmingen voor doorsturen zijn.</span><span class="sxs-lookup"><span data-stu-id="2ed78-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![De weergave Doorsturen van domeinen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="2ed78-211">**Gegevens tonen voor: Doorgestuurde gebruikers:** de volgende doorgestuurde gebruikers worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ed78-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="2ed78-212">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="2ed78-212">**Transport rule**</span></span>
  - <span data-ttu-id="2ed78-213">Het postvak met de regel voor Postvak IN doorsturen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![De weergave Doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="2ed78-215">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="2ed78-216">Detailtabelweergave voor het rapport Doorsturen</span><span class="sxs-lookup"><span data-stu-id="2ed78-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="2ed78-217">Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ed78-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="2ed78-218">**Forwarders:** de waarde **transportregel of** het postvak dat de regel voor Postvak IN voor doorsturen bevat.</span><span class="sxs-lookup"><span data-stu-id="2ed78-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="2ed78-219">**Type doorsturen:** de waarde van **de regel Postvak of** **Transportregel.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="2ed78-220">**Naam van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="2ed78-220">**Recipient name**</span></span>
- <span data-ttu-id="2ed78-221">**Domein van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="2ed78-221">**Recipient domain**</span></span>
- <span data-ttu-id="2ed78-222">**Details:** dit is de GUID-waarde van de regel voor de e-mailstroom, of de waarde RuleIdentity van de regel voor Postvak IN.</span><span class="sxs-lookup"><span data-stu-id="2ed78-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="2ed78-223">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-223">**Count**</span></span>
- <span data-ttu-id="2ed78-224">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="2ed78-224">**First forward date**</span></span>

<span data-ttu-id="2ed78-225">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2ed78-226">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="2ed78-227">Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="2ed78-227">Mailflow status report</span></span>

<span data-ttu-id="2ed78-228">Het **statusrapport Mailflow** is vergelijkbaar met het rapport Verzonden en ontvangen e-mail, [](#sent-and-received-email-report)met aanvullende informatie over e-mail die is toegestaan of geblokkeerd aan de rand.</span><span class="sxs-lookup"><span data-stu-id="2ed78-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="2ed78-229">Dit is het enige rapport met informatie over randbeveiliging en laat zien hoeveel e-mail is geblokkeerd voordat deze wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="2ed78-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2ed78-230">Het is belangrijk om te weten dat als een bericht naar vijf geadresseerden wordt verzonden, het als vijf verschillende berichten wordt geteld en niet als één bericht.</span><span class="sxs-lookup"><span data-stu-id="2ed78-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="2ed78-231">Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten en selecteert u \>  **het Mailflow-statusrapport.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="2ed78-232">Als u rechtstreeks naar het statusrapport van de **e-mailstroom wilt gaan,** opent u <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget Mailflow-statusrapport in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="2ed78-234">Typeweergave voor het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="2ed78-235">Wanneer u het rapport opent, is het **tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2ed78-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="2ed78-236">Deze weergave bevat standaard een grafiek en een gegevenstabel die zijn geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2ed78-237">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="2ed78-238">**Richting:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-238">**Direction**:</span></span>

  - <span data-ttu-id="2ed78-239">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="2ed78-239">**Inbound**</span></span>
  - <span data-ttu-id="2ed78-240">**Uitgaand**</span><span class="sxs-lookup"><span data-stu-id="2ed78-240">**Outbound**</span></span>
  - <span data-ttu-id="2ed78-241">**Rente-organisatie:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="2ed78-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2ed78-242">sender abc@domain.com verzendt naar ontvanger xyz@domain.com (afzonderlijk geteld van **binnenkomende** en **uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="2ed78-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="2ed78-243">**Typt** u:</span><span class="sxs-lookup"><span data-stu-id="2ed78-243">**Type**:</span></span>

  - <span data-ttu-id="2ed78-244">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="2ed78-244">**Good mail**</span></span>
  - <span data-ttu-id="2ed78-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="2ed78-245">**Malware**</span></span>
  - <span data-ttu-id="2ed78-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="2ed78-246">**Spam**</span></span>
  - <span data-ttu-id="2ed78-247">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="2ed78-247">**Edge protection**</span></span>
  - <span data-ttu-id="2ed78-248">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-248">**Rule messages**</span></span>
  - <span data-ttu-id="2ed78-249">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="2ed78-249">**Phishing email**</span></span>

<span data-ttu-id="2ed78-250">De grafiek is ingedeeld op basis van **de typewaarden.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="2ed78-251">U kunt deze filters wijzigen door te klikken op **Filter** of door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="2ed78-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="2ed78-252">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2ed78-252">The data table contains the following information:</span></span>

- <span data-ttu-id="2ed78-253">**Richting**</span><span class="sxs-lookup"><span data-stu-id="2ed78-253">**Direction**</span></span>
- <span data-ttu-id="2ed78-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ed78-254">**Type**</span></span>
- <span data-ttu-id="2ed78-255">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="2ed78-255">**24 hours**</span></span>
- <span data-ttu-id="2ed78-256">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-256">**3 days**</span></span>
- <span data-ttu-id="2ed78-257">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-257">**7 days**</span></span>
- <span data-ttu-id="2ed78-258">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-258">**15 days**</span></span>
- <span data-ttu-id="2ed78-259">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-259">**30 days**</span></span>

<span data-ttu-id="2ed78-260">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="2ed78-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="2ed78-261">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Risicobeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2ed78-262">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Risicobeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="2ed78-263">**Spamdetecties:** met deze selectie gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="2ed78-264">**Geblokkeerde spam in Edge:** met deze selectie gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2ed78-265">**Exporteren:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-265">**Export**:</span></span>

<span data-ttu-id="2ed78-266">Voor de detailweergave kunt u slechts gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2ed78-267">Dus als u gegevens zeven dagen lang wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2ed78-268">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2ed78-269">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2ed78-270">Typeweergave in het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="2ed78-271">Richtingsweergave voor het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="2ed78-272">Als u op het **tabblad Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="2ed78-273">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="2ed78-274">U kunt deze filters wijzigen door te klikken op **Filter** of door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="2ed78-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="2ed78-275">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="2ed78-276">De gegevenstabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="2ed78-277">De **optie Kies een categorie voor meer informatie** over beschikbare selecties en gedrag is hetzelfde als de weergave **Type.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="2ed78-278">**Exporteren:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-278">**Export**:</span></span>

<span data-ttu-id="2ed78-279">Voor de detailweergave kunt u slechts gegevens voor één dag exporteren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="2ed78-280">Dus als u gegevens zeven dagen lang wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="2ed78-281">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2ed78-282">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="2ed78-283">Richtingsweergave in het statusrapport Mailflow</span><span class="sxs-lookup"><span data-stu-id="2ed78-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="2ed78-284">Trechterweergave voor het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="2ed78-285">In **de weergave** Trechter ziet u hoe met de beveiligingsfuncties voor e-mail van Microsoft binnenkomende en uitgaande e-mail in uw organisatie wordt gefilterd.</span><span class="sxs-lookup"><span data-stu-id="2ed78-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="2ed78-286">Het bevat details over het totale aantal e-mails en hoe de geconfigureerde functies voor bedreigingsbeveiliging, waaronder randbeveiliging, anti-malware, anti-phishing, anti-spam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="2ed78-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="2ed78-287">Als u op het **tabblad Trechter** klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die zijn geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2ed78-288">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2ed78-289">**Richting:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-289">**Direction**:</span></span>

  - <span data-ttu-id="2ed78-290">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="2ed78-290">**Inbound**</span></span>
  - <span data-ttu-id="2ed78-291">**Uitgaand**</span><span class="sxs-lookup"><span data-stu-id="2ed78-291">**Outbound**</span></span>
  - <span data-ttu-id="2ed78-292">**Rente-organisatie:** dit aantal geldt voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat abc@domain.com berichten naar de ontvanger xyz@domain.com (geteld afzonderlijk van binnenkomende en uitgaande).</span><span class="sxs-lookup"><span data-stu-id="2ed78-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="2ed78-293">Filteren kan in de statistische weergave en de gegevenstabelweergave 90 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2ed78-294">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2ed78-295">In dit diagram ziet u het aantal e-mailberichten, georganiseerd op:</span><span class="sxs-lookup"><span data-stu-id="2ed78-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="2ed78-296">**Totaal aantal e-mailberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-296">**Total email**</span></span>
- <span data-ttu-id="2ed78-297">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="2ed78-297">**Email after edge protection**</span></span>
- <span data-ttu-id="2ed78-298">**E-mail na anti-malware, bestandsreputatie, bestandstypeblokkering**</span><span class="sxs-lookup"><span data-stu-id="2ed78-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="2ed78-299">**E-mail na anti-phish, URL-reputatie, merk imitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="2ed78-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="2ed78-300">**E-mail na antispamfilters, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="2ed78-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="2ed78-301">**E-mail na gebruikers- en domein imitatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2ed78-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="2ed78-302">**E-mail na bestands- en URL-detonatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2ed78-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="2ed78-303">**E-mail die na de bezorgingsbeveiliging is gedetecteerd (URL-kliktijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="2ed78-304"><sup>Alleen 1</sup> Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2ed78-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="2ed78-305">Als u de e-mail die wordt gefilterd op EOP of Defender voor Office 365 afzonderlijk wilt bekijken, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="2ed78-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="2ed78-306">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="2ed78-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2ed78-307">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-307">**Date**</span></span>
- <span data-ttu-id="2ed78-308">**Totaal aantal e-mailberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-308">**Total email**</span></span>
- <span data-ttu-id="2ed78-309">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="2ed78-309">**Edge protection**</span></span>
- <span data-ttu-id="2ed78-310">**Anti-malware, bestandsreputatie, bestandstypeblokkering:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="2ed78-311">**Bestandsreputatie:** berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="2ed78-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="2ed78-312">**Bestandstypeblokkering:** berichten die zijn gefilterd vanwege het type schadelijk bestand dat is geïdentificeerd in het bericht.</span><span class="sxs-lookup"><span data-stu-id="2ed78-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="2ed78-313">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="2ed78-314">**URL-reputatie:** berichten gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="2ed78-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="2ed78-315">**Merk imitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende afzenders die zich voordoen als afzenders.</span><span class="sxs-lookup"><span data-stu-id="2ed78-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="2ed78-316">**Anti-spoofing:** berichten die zijn gefilterd omdat het bericht een domein probeert te vervalsen waar de geadresseerde deel van uit maakt, of een domein dat niet in bezit is van de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="2ed78-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="2ed78-317">**Antispamfilters, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="2ed78-318">**Bulkmailfilter:** berichten die zijn gefilterd vanwege een poging om bulkmail af te leveren bij de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2ed78-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="2ed78-319">**Imitatie van gebruikers en domeinen (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="2ed78-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2ed78-320">**Gebruikers imitatie:** berichten gefilterd vanwege een poging om een gebruiker (afzender van bericht) te imiteren die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="2ed78-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="2ed78-321">**Domein imitatie:** berichten gefilterd vanwege een poging om een domein te imiteren dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="2ed78-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="2ed78-322">**Detonatie van bestanden en URL's (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="2ed78-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="2ed78-323">**Bestandsdetonatie:** berichten die zijn gefilterd op een beleid voor veilige bijlagen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="2ed78-324">**URL-detonatie:** bericht gefilterd op een beleid voor veilige koppelingen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="2ed78-325">**Beveiliging na aflevering en ZAP (ATP) of ZAP (EOP)**: ZAP geeft automatisch purge van nul uur aan.</span><span class="sxs-lookup"><span data-stu-id="2ed78-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="2ed78-326">Als u een rij in de gegevenstabel selecteert, worden de e-mailberichten in de flyout verder uitsplitsing weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2ed78-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2ed78-327">**Exporteren:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-327">**Export**:</span></span>

<span data-ttu-id="2ed78-328">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="2ed78-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="2ed78-329">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2ed78-330">**Details (met gegevens voor de afgelopen 30 dagen)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2ed78-331">Kies **een** bereik onder Datum en klik op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2ed78-332">Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="2ed78-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2ed78-333">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2ed78-334">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2ed78-335">Trechterweergave in het statusrapport Mailflow</span><span class="sxs-lookup"><span data-stu-id="2ed78-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="2ed78-336">Technische weergave voor het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="2ed78-337">De **weergave Tech** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="2ed78-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="2ed78-338">In de grafiek kunt u zien hoe berichten zijn gecategoriseerd in de verschillende fasen van risicobeveiliging.</span><span class="sxs-lookup"><span data-stu-id="2ed78-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="2ed78-339">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="2ed78-340">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="2ed78-341">**Richting:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-341">**Direction**:</span></span>

  - <span data-ttu-id="2ed78-342">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="2ed78-342">**Inbound**</span></span>
  - <span data-ttu-id="2ed78-343">**Uitgaand**</span><span class="sxs-lookup"><span data-stu-id="2ed78-343">**Outbound**</span></span>
  - <span data-ttu-id="2ed78-344">**Rente-organisatie:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="2ed78-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="2ed78-345">sender abc@domain.com verzendt naar ontvanger xyz@domain.com (afzonderlijk geteld van inkomende en uitgaande)</span><span class="sxs-lookup"><span data-stu-id="2ed78-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="2ed78-346">Filteren kan in de statistische weergave en de gegevenstabelweergave 90 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="2ed78-347">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="2ed78-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="2ed78-348">In dit diagram worden berichten weergegeven die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="2ed78-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="2ed78-349">**Totaal aantal e-mailberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-349">**Total email**</span></span>
- <span data-ttu-id="2ed78-350">**Edge toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="2ed78-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="2ed78-351">**Geen malware,** **detectie van veilige bijlagen,** <sup>\*</sup> detectie van **antimalware-engine en** **regelberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="2ed78-352">**Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection,** and **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="2ed78-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="2ed78-353">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2ed78-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="2ed78-354">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="2ed78-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="2ed78-355">**Niet-schadelijke e-mail,** **detectie van veilige koppelingen** en <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="2ed78-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="2ed78-356"><sup>\*</sup> Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2ed78-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="2ed78-357">Wanneer u de muisaanwijzer op een categorie in de grafiek beweegt, ziet u het aantal berichten in die categorie.</span><span class="sxs-lookup"><span data-stu-id="2ed78-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="2ed78-358">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="2ed78-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="2ed78-359">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-359">**Date**</span></span>
- <span data-ttu-id="2ed78-360">**Totaal aantal e-mailberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-360">**Total email**</span></span>
- <span data-ttu-id="2ed78-361">**Gefilterd op Edge**</span><span class="sxs-lookup"><span data-stu-id="2ed78-361">**Edge filtered**</span></span>
- <span data-ttu-id="2ed78-362">**Antimalware-engine, veilige bijlagen, regel gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="2ed78-363">**Regel gefilterd:** berichten die zijn gefilterd vanwege regels voor de e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="2ed78-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="2ed78-364">**DMARC, imitatie, spoofing, phish gefilterd:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="2ed78-365">**DMARC: Berichten** gefilterd als gevolg van het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="2ed78-366">**DETECTIE VAN URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="2ed78-366">**URL detonation detection**</span></span>
- <span data-ttu-id="2ed78-367">**Antispam gefilterd**</span><span class="sxs-lookup"><span data-stu-id="2ed78-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="2ed78-368">**ZAP is verwijderd**</span><span class="sxs-lookup"><span data-stu-id="2ed78-368">**ZAP removed**</span></span>
- <span data-ttu-id="2ed78-369">**Detectie via veilige koppelingen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="2ed78-370">Als u een rij in de gegevenstabel selecteert, worden de e-mailberichten in de flyout verder uitsplitsing weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2ed78-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="2ed78-371">**Exporteren:**</span><span class="sxs-lookup"><span data-stu-id="2ed78-371">**Export**:</span></span>

<span data-ttu-id="2ed78-372">Als u op **Exporteren klikt,** kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="2ed78-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="2ed78-373">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="2ed78-374">**Details (met gegevens voor de afgelopen 30 dagen)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="2ed78-375">Kies **een** bereik onder Datum en klik op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="2ed78-376">Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="2ed78-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="2ed78-377">Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="2ed78-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="2ed78-378">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2ed78-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="2ed78-379">Technische weergave in het Mailflow-statusrapport</span><span class="sxs-lookup"><span data-stu-id="2ed78-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="2ed78-380">Rapport verzonden en ontvangen e-mail</span><span class="sxs-lookup"><span data-stu-id="2ed78-380">Sent and received email report</span></span>

<span data-ttu-id="2ed78-381">Het **rapport Verzonden** en ontvangen e-mail is een slim rapport met informatie over binnenkomende en uitgaande e-mail, inclusief spamdetecties, malware en e-mail die wordt geïdentificeerd als 'goed'.</span><span class="sxs-lookup"><span data-stu-id="2ed78-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="2ed78-382">Het verschil tussen dit rapport en het [Mailflow-statusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging. Het is belangrijk om te weten dat als een bericht naar vijf geadresseerden wordt verzonden, dit als één bericht wordt geteld.</span><span class="sxs-lookup"><span data-stu-id="2ed78-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="2ed78-383">Filteren kan 90 dagen duren voor de statistische weergave en de detailweergave van het rapport.</span><span class="sxs-lookup"><span data-stu-id="2ed78-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="2ed78-384">Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u \>  **Verzonden en ontvangen e-mail.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="2ed78-385">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![De widget Verzonden en ontvangen e-mail in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2ed78-387">Rapportweergave voor het rapport Verzonden en ontvangen e-mail</span><span class="sxs-lookup"><span data-stu-id="2ed78-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="2ed78-388">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="2ed78-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2ed78-389">**Afbreken op: Type:** De grafiek bevat alle beschikbare categorieën:</span><span class="sxs-lookup"><span data-stu-id="2ed78-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="2ed78-390">**Totaal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-390">**Total**</span></span>
  - <span data-ttu-id="2ed78-391">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="2ed78-391">**Good mail**</span></span>
  - <span data-ttu-id="2ed78-392">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2ed78-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="2ed78-393">**Spamdetecties**</span><span class="sxs-lookup"><span data-stu-id="2ed78-393">**Spam detections**</span></span>
  - <span data-ttu-id="2ed78-394">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-394">**Rule messages**</span></span>
  - <span data-ttu-id="2ed78-395">**Geavanceerde malware** (Microsoft Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="2ed78-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="2ed78-396">Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, ziet u de details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="2ed78-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Weergave Typen in het rapport Verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="2ed78-398">**Op te delen met: Richting:** in de grafiek ziet u **het totaal,** **de** binnenkomende en **uitgaande** gegevens.</span><span class="sxs-lookup"><span data-stu-id="2ed78-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="2ed78-399">Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, ziet u de details voor die dag.</span><span class="sxs-lookup"><span data-stu-id="2ed78-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Richtingsweergave in het rapport Verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="2ed78-401">**Inzoomen op** \> **Malware (anti-malware)**: met deze selectie gaat u naar de [malwaredetecties in het e-mailrapport.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="2ed78-402">**Inzoomen op** \> **Spamdetecties:** hiermee gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="2ed78-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="2ed78-403">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2ed78-404">**Begindatum** **en einddatum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="2ed78-405">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-405">Direction values</span></span>
- <span data-ttu-id="2ed78-406">Typewaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-406">Type values</span></span>

<span data-ttu-id="2ed78-407">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="2ed78-408">Tabelweergave Details voor het rapport Verzonden en ontvangen e-mail</span><span class="sxs-lookup"><span data-stu-id="2ed78-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="2ed78-409">Als u klikt **op de tabel Details weergeven** in Op delen **door:** Richting of Opbreken **door:** Richtingsweergave, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ed78-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="2ed78-410">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-410">**Date (UTC)**</span></span>
- <span data-ttu-id="2ed78-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ed78-411">**Type**</span></span>
- <span data-ttu-id="2ed78-412">**Richting**</span><span class="sxs-lookup"><span data-stu-id="2ed78-412">**Direction**</span></span>
- <span data-ttu-id="2ed78-413">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="2ed78-413">**Message count**</span></span>

<span data-ttu-id="2ed78-414">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="2ed78-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="2ed78-415">**Begindatum** **en einddatum**</span><span class="sxs-lookup"><span data-stu-id="2ed78-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="2ed78-416">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-416">Direction values</span></span>
- <span data-ttu-id="2ed78-417">Typewaarden</span><span class="sxs-lookup"><span data-stu-id="2ed78-417">Type values</span></span>

<span data-ttu-id="2ed78-418">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="2ed78-419">Top senders and recipients report</span><span class="sxs-lookup"><span data-stu-id="2ed78-419">Top senders and recipients report</span></span>

<span data-ttu-id="2ed78-420">Het **rapport met de belangrijkste afzenders en geadresseerden** is een cirkeldiagram met de belangrijkste afzenders en geadresseerden van uw e-mail.</span><span class="sxs-lookup"><span data-stu-id="2ed78-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="2ed78-421">Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u de belangrijkste \>  **afzenders en geadresseerden.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="2ed78-422">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="2ed78-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![De belangrijkste widget voor afzenders en geadresseerden in het dashboard Rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2ed78-424">Rapportweergave voor het rapport met de belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="2ed78-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="2ed78-425">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="2ed78-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="2ed78-426">**Gegevens voor belangrijkste \> afzenders van e-mailberichten tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="2ed78-427">**Gegevens voor belangrijkste \> e-mailontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="2ed78-428">**Gegevens voor belangrijkste \> geadresseerden van ongewenste e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="2ed78-429">**Gegevens tonen voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2ed78-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="2ed78-430">**Gegevens tonen voor \> belangrijkste malwareontvangers (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="2ed78-431">De samenstelling van het cirkeldiagram verandert op basis van deze selecties.</span><span class="sxs-lookup"><span data-stu-id="2ed78-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="2ed78-432">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u het aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="2ed78-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="2ed78-433">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Cirkeldiagram in rapportweergave in het rapport Met de belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="2ed78-435">Detailtabelweergave voor het rapport Met de belangrijkste afzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="2ed78-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="2ed78-436">Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="2ed78-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="2ed78-437">**Gegevens voor belangrijkste \> afzenders van e-mailberichten tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="2ed78-438">**Belangrijkste afzenders van e-mail**</span><span class="sxs-lookup"><span data-stu-id="2ed78-438">**Top mail senders**</span></span>
  - <span data-ttu-id="2ed78-439">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-439">**Count**</span></span>

- <span data-ttu-id="2ed78-440">**Gegevens voor belangrijkste \> e-mailontvangers tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="2ed78-441">**Belangrijkste e-mailontvangers**</span><span class="sxs-lookup"><span data-stu-id="2ed78-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="2ed78-442">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-442">**Count**</span></span>

- <span data-ttu-id="2ed78-443">**Gegevens voor belangrijkste \> geadresseerden van ongewenste e-mail tonen**</span><span class="sxs-lookup"><span data-stu-id="2ed78-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="2ed78-444">**Belangrijkste geadresseerden voor ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="2ed78-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="2ed78-445">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-445">**Count**</span></span>

- <span data-ttu-id="2ed78-446">**Gegevens tonen voor \> Belangrijkste ontvangers van malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="2ed78-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="2ed78-447">**Belangrijkste ontvangers van malware**</span><span class="sxs-lookup"><span data-stu-id="2ed78-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="2ed78-448">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-448">**Count**</span></span>

- <span data-ttu-id="2ed78-449">**Gegevens tonen voor \> belangrijkste malwareontvangers (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="2ed78-450">**Belangrijkste ontvangers van malware (Defender voor Office 365)**</span><span class="sxs-lookup"><span data-stu-id="2ed78-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="2ed78-451">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="2ed78-451">**Count**</span></span>

<span data-ttu-id="2ed78-452">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="2ed78-453">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="2ed78-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="2ed78-454">Welke machtigingen zijn nodig om deze rapporten te bekijken?</span><span class="sxs-lookup"><span data-stu-id="2ed78-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="2ed78-455">Als u de rapporten in dit artikel wilt bekijken en gebruiken, moet u lid zijn van een van de volgende rollengroepen in het beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="2ed78-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2ed78-456">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="2ed78-456">**Organization Management**</span></span>
- <span data-ttu-id="2ed78-457">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="2ed78-457">**Security Administrator**</span></span>
- <span data-ttu-id="2ed78-458">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="2ed78-458">**Security Reader**</span></span>
- <span data-ttu-id="2ed78-459">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="2ed78-459">**Global Reader**</span></span>

<span data-ttu-id="2ed78-460">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2ed78-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2ed78-461">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ed78-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2ed78-462">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2ed78-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ed78-463">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2ed78-463">Related topics</span></span>

[<span data-ttu-id="2ed78-464">Slimme rapporten en inzichten in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="2ed78-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="2ed78-465">Inzichten in e-mailstroom in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="2ed78-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="2ed78-466">Beveiligingsrapporten voor e-mail weergeven in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="2ed78-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="2ed78-467">Rapporten voor Microsoft Defender voor Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="2ed78-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
