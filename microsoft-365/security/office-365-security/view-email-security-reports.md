---
title: Beveiligingsrapporten voor e-mail weergeven
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze de e-mailbeveiligingsrapporten kunnen vinden en gebruiken die beschikbaar zijn in de Microsoft 365 Defender-portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029545"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="307e4-103">E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="307e4-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="307e4-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="307e4-104">**Applies to**</span></span>
- [<span data-ttu-id="307e4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="307e4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="307e4-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="307e4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="307e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="307e4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="307e4-108">Er zijn diverse rapporten beschikbaar in de Microsoft 365 Defender-portal om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie <https://security.microsoft.com> beschermen.</span><span class="sxs-lookup"><span data-stu-id="307e4-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="307e4-109">Als u de benodigde machtigingen [hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken  in de Microsoft 365 Defender-portal door naar Rapporten E-mail & samenwerking e-mail \>  \> **& samenwerkingsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="307e4-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-110">Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="307e4-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender-portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="307e4-112">Voor sommige rapporten op de pagina **E-& samenwerkingsrapporten** is Microsoft Defender voor Office 365 vereist.</span><span class="sxs-lookup"><span data-stu-id="307e4-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="307e4-113">Zie Defender voor [Office 365-rapporten weergeven in de Microsoft 365 Defender-portal](view-reports-for-mdo.md)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="307e4-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="307e4-114">Rapporten die zijn gerelateerd aan e-mailstroom, zijn nu in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="307e4-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="307e4-115">Zie E-mailstroomrapporten in het [nieuwe Exchange-beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="307e4-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="307e4-116">Rapport over gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="307e4-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="307e4-117">Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="307e4-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="307e4-118">Het is niet beschikbaar in zelfstandige EOP-organisaties (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="307e4-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="307e4-119">In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt.</span><span class="sxs-lookup"><span data-stu-id="307e4-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="307e4-120">Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="307e4-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="307e4-121">Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts.</span><span class="sxs-lookup"><span data-stu-id="307e4-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="307e4-122">Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Voor gecompromitteerde gebruikers op de pagina E-mail & samenwerkingsrapporten](../../media/compromised-users-report-widget.png)

<span data-ttu-id="307e4-124">De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="307e4-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="307e4-125">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-126">Zoek op **de pagina & samenwerkingsrapporten** naar Gecompromitteerde **gebruikers** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="307e4-127">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="307e4-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="307e4-128">Op de pagina Gecompromitteerd gebruikers kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven: </span><span class="sxs-lookup"><span data-stu-id="307e4-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="307e4-129">**Datum (UTC)**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="307e4-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="307e4-130">**Activiteit**:</span><span class="sxs-lookup"><span data-stu-id="307e4-130">**Activity**:</span></span>
  - <span data-ttu-id="307e4-131">**Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="307e4-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="307e4-132">**Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.</span><span class="sxs-lookup"><span data-stu-id="307e4-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="307e4-133">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="307e4-135">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="307e4-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="307e4-136">**Aanmaaktijd**</span><span class="sxs-lookup"><span data-stu-id="307e4-136">**Creation time**</span></span>
- <span data-ttu-id="307e4-137">**Gebruikers-id**</span><span class="sxs-lookup"><span data-stu-id="307e4-137">**User ID**</span></span>
- <span data-ttu-id="307e4-138">**Actie**</span><span class="sxs-lookup"><span data-stu-id="307e4-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="307e4-139">Rapport met exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="307e4-139">Exchange transport rule report</span></span>

<span data-ttu-id="307e4-140">Het **rapport Exchange-transportregel** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="307e4-141">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-142">Zoek op **de pagina E-& samenwerkingsrapporten** **naar Exchange-transportregel** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="307e4-143">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="307e4-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-transportregelwidget op de pagina E-mail & samenwerkingsrapporten](../../media/transport-rule-report-widget.png)

<span data-ttu-id="307e4-145">Op de rapportpagina van de **Exchange-transportregel** worden de beschikbare grafieken en gegevens in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="307e4-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="307e4-146">Grafiek uitsplitsing op richting</span><span class="sxs-lookup"><span data-stu-id="307e4-146">Chart breakdown by Direction</span></span>

![Richtingsweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="307e4-148">Als u Grafiek **uitsplitsing op richting selecteert,** zijn de volgende grafieken beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="307e4-149">**Gegevens weergeven op exchange-transportregels:** het  aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="307e4-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="307e4-150">**Gegevens weergeven op DLP Exchange-transportregels:**  het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door DLP-regels (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="307e4-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="307e4-151">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="307e4-152">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-152">**Date**</span></span>
- <span data-ttu-id="307e4-153">**DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**</span><span class="sxs-lookup"><span data-stu-id="307e4-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="307e4-154">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="307e4-154">**Transport rule**</span></span>
- <span data-ttu-id="307e4-155">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-155">**Subject**</span></span>
- <span data-ttu-id="307e4-156">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-156">**Sender address**</span></span>
- <span data-ttu-id="307e4-157">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="307e4-157">**Recipient address**</span></span>
- <span data-ttu-id="307e4-158">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="307e4-158">**Severity**</span></span>
- <span data-ttu-id="307e4-159">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-159">**Direction**</span></span>

<span data-ttu-id="307e4-160">U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="307e4-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="307e4-161">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-162">**Richting:** **Uitgaande en Inkomende** </span><span class="sxs-lookup"><span data-stu-id="307e4-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="307e4-163">**Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**</span><span class="sxs-lookup"><span data-stu-id="307e4-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="307e4-164">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="307e4-165">Uitsplitsing van grafieken op ernst</span><span class="sxs-lookup"><span data-stu-id="307e4-165">Chart breakdown by Severity</span></span>

![Ernstweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="307e4-167">Als u Grafiek **uitsplitsing op ernst selecteert,** zijn de volgende grafieken beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="307e4-168">**Gegevens weergeven op exchange-transportregels:** het aantal berichten met hoge **ernst,** gemiddelde **ernst** en **berichten met lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="307e4-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="307e4-169">U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="307e4-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="307e4-170">Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="307e4-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="307e4-171">**Gegevens weergeven op DLP Exchange-transportregels:** het aantal berichten  met hoge **ernst,** gemiddelde ernst en lage ernst die zijn beïnvloed door DLP-regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="307e4-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="307e4-172">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="307e4-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-173">**Date**</span></span>
- <span data-ttu-id="307e4-174">**DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**</span><span class="sxs-lookup"><span data-stu-id="307e4-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="307e4-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="307e4-175">**Transport rule**</span></span>
- <span data-ttu-id="307e4-176">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-176">**Subject**</span></span>
- <span data-ttu-id="307e4-177">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-177">**Sender address**</span></span>
- <span data-ttu-id="307e4-178">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="307e4-178">**Recipient address**</span></span>
- <span data-ttu-id="307e4-179">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="307e4-179">**Severity**</span></span>
- <span data-ttu-id="307e4-180">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-180">**Direction**</span></span>

<span data-ttu-id="307e4-181">U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="307e4-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="307e4-182">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-183">**Richting:** **Uitgaande en Inkomende** </span><span class="sxs-lookup"><span data-stu-id="307e4-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="307e4-184">**Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**</span><span class="sxs-lookup"><span data-stu-id="307e4-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="307e4-185">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="307e4-186">Doorsturen van rapport</span><span class="sxs-lookup"><span data-stu-id="307e4-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="307e4-187">Het **rapport Doorsturen** is nu beschikbaar in het EAC.</span><span class="sxs-lookup"><span data-stu-id="307e4-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="307e4-188">Zie Rapport Automatisch doorgestuurde berichten in het nieuwe EAC voor [meer informatie.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="307e4-189">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="307e4-189">Mailflow status report</span></span>

<span data-ttu-id="307e4-190">Het **mailflowstatusrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, spamdetecties, malware, e-mail die als 'goed' is geïdentificeerd en informatie over e-mail die is toegestaan of geblokkeerd op de rand.</span><span class="sxs-lookup"><span data-stu-id="307e4-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="307e4-191">Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat e-mail wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="307e4-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="307e4-192">Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="307e4-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="307e4-193">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-194">Zoek op **de & e-mail met samenwerkingsrapporten** de **statusoverzicht van Mailflow** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="307e4-195">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="307e4-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Overzichtswidget Mailflow-status op de pagina E-mail & samenwerkingsrapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="307e4-197">Typweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="307e4-197">Type view for the Mailflow status report</span></span>

![Weergave typen in het rapport Mailflow-status](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="307e4-199">Op de **pagina Mailflow-statusrapport** is het **tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="307e4-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="307e4-200">Deze weergave bevat standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="307e4-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="307e4-201">**Datum (UTC)** De afgelopen 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="307e4-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="307e4-202">**E-mailrichting**:</span><span class="sxs-lookup"><span data-stu-id="307e4-202">**Mail direction**:</span></span>
  - <span data-ttu-id="307e4-203">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="307e4-203">**Inbound**</span></span>
  - <span data-ttu-id="307e4-204">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="307e4-204">**Outbound**</span></span>
  - <span data-ttu-id="307e4-205">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="307e4-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="307e4-206">afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="307e4-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="307e4-207">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="307e4-207">**Type**:</span></span>
  - <span data-ttu-id="307e4-208">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-208">**Good mail**</span></span>
  - <span data-ttu-id="307e4-209">**Malware**</span><span class="sxs-lookup"><span data-stu-id="307e4-209">**Malware**</span></span>
  - <span data-ttu-id="307e4-210">**Spam**</span><span class="sxs-lookup"><span data-stu-id="307e4-210">**Spam**</span></span>
  - <span data-ttu-id="307e4-211">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="307e4-211">**Edge protection**</span></span>
  - <span data-ttu-id="307e4-212">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="307e4-212">**Rule messages**</span></span>
  - <span data-ttu-id="307e4-213">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-213">**Phishing email**</span></span>
- <span data-ttu-id="307e4-214">**Domein:** **Alles**</span><span class="sxs-lookup"><span data-stu-id="307e4-214">**Domain**: **All**</span></span>

<span data-ttu-id="307e4-215">De grafiek wordt ingedeeld op basis van **de waarden Type.**</span><span class="sxs-lookup"><span data-stu-id="307e4-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="307e4-216">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="307e4-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="307e4-217">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="307e4-218">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-218">**Direction**</span></span>
- <span data-ttu-id="307e4-219">**Type**</span><span class="sxs-lookup"><span data-stu-id="307e4-219">**Type**</span></span>
- <span data-ttu-id="307e4-220">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="307e4-220">**24 hours**</span></span>
- <span data-ttu-id="307e4-221">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="307e4-221">**3 days**</span></span>
- <span data-ttu-id="307e4-222">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="307e4-222">**7 days**</span></span>
- <span data-ttu-id="307e4-223">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="307e4-223">**15 days**</span></span>
- <span data-ttu-id="307e4-224">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="307e4-224">**30 days**</span></span>

<span data-ttu-id="307e4-225">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="307e4-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="307e4-226">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="307e4-227">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="307e4-228">**Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="307e4-229">**Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="307e4-230">Exporteren vanuit de weergave Type</span><span class="sxs-lookup"><span data-stu-id="307e4-230">Export from Type view</span></span>

<span data-ttu-id="307e4-231">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="307e4-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="307e4-232">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="307e4-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="307e4-233">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="307e4-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="307e4-234">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="307e4-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="307e4-235">Richtingsweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="307e4-235">Direction view for the Mailflow status report</span></span>

![Richtingsweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="307e4-237">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="307e4-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="307e4-238">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="307e4-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="307e4-239">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="307e4-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="307e4-240">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="307e4-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="307e4-241">De detailtabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="307e4-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="307e4-242">De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.</span><span class="sxs-lookup"><span data-stu-id="307e4-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="307e4-243">Exporteren vanuit de richtingsweergave</span><span class="sxs-lookup"><span data-stu-id="307e4-243">Export from Direction view</span></span>

<span data-ttu-id="307e4-244">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="307e4-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="307e4-245">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="307e4-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="307e4-246">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="307e4-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="307e4-247">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="307e4-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="307e4-248">Trechterweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="307e4-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="307e4-249">In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="307e4-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="307e4-250">Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="307e4-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![Trechterweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="307e4-252">Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="307e4-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="307e4-253">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="307e4-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="307e4-254">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="307e4-254">**Direction**:</span></span>
  - <span data-ttu-id="307e4-255">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="307e4-255">**Inbound**</span></span>
  - <span data-ttu-id="307e4-256">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="307e4-256">**Outbound**</span></span>
  - <span data-ttu-id="307e4-257">**Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).</span><span class="sxs-lookup"><span data-stu-id="307e4-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="307e4-258">De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="307e4-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="307e4-259">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="307e4-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="307e4-260">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="307e4-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="307e4-261">In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="307e4-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="307e4-262">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-262">**Total email**</span></span>
- <span data-ttu-id="307e4-263">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="307e4-263">**Email after edge protection**</span></span>
- <span data-ttu-id="307e4-264">**Regel E-mail na transport** (regel voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="307e4-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="307e4-265">**E-mail na anti-malware, bestandsreputatie, bestandstypeblok**</span><span class="sxs-lookup"><span data-stu-id="307e4-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="307e4-266">**E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="307e4-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="307e4-267">**E-mail na antispam, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="307e4-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="307e4-268">**E-mail na gebruikers- en domein-imitatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-269">**E-mail na bestand en URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-270">**E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="307e4-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="307e4-271"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="307e4-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="307e4-272">Als u het e-mailbericht wilt weergeven dat is gefilterd op EOP of Defender Office 365 afzonderlijk, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="307e4-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="307e4-273">De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="307e4-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="307e4-274">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-274">**Date**</span></span>
- <span data-ttu-id="307e4-275">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-275">**Total email**</span></span>
- <span data-ttu-id="307e4-276">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="307e4-276">**Edge protection**</span></span>
- <span data-ttu-id="307e4-277">**Anti-malware, bestandsreputatie, bestandstypeblok:**</span><span class="sxs-lookup"><span data-stu-id="307e4-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="307e4-278">**Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="307e4-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="307e4-279">**Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="307e4-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="307e4-280">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="307e4-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="307e4-281">**URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="307e4-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="307e4-282">**Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.</span><span class="sxs-lookup"><span data-stu-id="307e4-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="307e4-283">**Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.</span><span class="sxs-lookup"><span data-stu-id="307e4-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="307e4-284">**Antispam, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="307e4-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="307e4-285">**Bulkmailfilters:** Berichten gefilterd op basis van de drempel voor bulksgewijs klagen (BCL) in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="307e4-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="307e4-286">**Gebruikers- en domein-imitatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="307e4-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="307e4-287">**Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="307e4-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="307e4-288">**Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="307e4-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="307e4-289">**Bestands- en URL-detonatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="307e4-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="307e4-290">**Bestandsdetonatie:** Berichten gefilterd op een Safe bijlagenbeleid.</span><span class="sxs-lookup"><span data-stu-id="307e4-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="307e4-291">**URL-detonatie:** bericht gefilterd door een Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="307e4-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="307e4-292">**Bescherming na bezorging en ZAP (ATP) of ZAP (EOP)**: Automatische purge (ZAP) van nul uur voor malware, spam en phishing.</span><span class="sxs-lookup"><span data-stu-id="307e4-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="307e4-293">Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="307e4-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="307e4-294">Exporteren vanuit de trechterweergave</span><span class="sxs-lookup"><span data-stu-id="307e4-294">Export from Funnel view</span></span>

<span data-ttu-id="307e4-295">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="307e4-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="307e4-296">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="307e4-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="307e4-297">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="307e4-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="307e4-298">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="307e4-299">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="307e4-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="307e4-300">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="307e4-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="307e4-301">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="307e4-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="307e4-302">Technische weergave voor het mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="307e4-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="307e4-303">De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="307e4-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="307e4-304">In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="307e4-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="307e4-305">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="307e4-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="307e4-306">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="307e4-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="307e4-307">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="307e4-307">**Direction**:</span></span>
  - <span data-ttu-id="307e4-308">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="307e4-308">**Inbound**</span></span>
  - <span data-ttu-id="307e4-309">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="307e4-309">**Outbound**</span></span>
  - <span data-ttu-id="307e4-310">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="307e4-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="307e4-311">afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)</span><span class="sxs-lookup"><span data-stu-id="307e4-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="307e4-312">De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="307e4-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="307e4-313">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="307e4-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="307e4-314">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="307e4-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="307e4-315">In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="307e4-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="307e4-316">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-316">**Total email**</span></span>
- <span data-ttu-id="307e4-317">**Rand toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="307e4-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="307e4-318">**Transportregel toestaan** en **Transportregel gefilterd** (regels voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="307e4-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="307e4-319">**Geen malware,** **Safe detectie van** bijlagen en detectie van <sup>\*</sup> **anti-malware-engine**</span><span class="sxs-lookup"><span data-stu-id="307e4-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="307e4-320">**Geen phish,** **DMARC-fout,** **imitatiedetectie,** <sup>\*</sup> **spoofdetectie** en **Phish-detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="307e4-321">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-322">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="307e4-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="307e4-323">**Niet-schadelijke e-mail,** **Safe koppelingendetectie** <sup>\*</sup> en **ZAP**</span><span class="sxs-lookup"><span data-stu-id="307e4-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="307e4-324"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="307e4-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="307e4-325">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.</span><span class="sxs-lookup"><span data-stu-id="307e4-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="307e4-326">De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="307e4-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="307e4-327">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="307e4-327">**Date (UTC)**</span></span>
- <span data-ttu-id="307e4-328">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-328">**Total email**</span></span>
- <span data-ttu-id="307e4-329">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="307e4-329">**Edge filtered**</span></span>
- <span data-ttu-id="307e4-330">**Regelberichten:** Berichten die zijn gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="307e4-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="307e4-331">**Anti-malware engine**, **Safe Bijlagen:** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="307e4-332">**DMARC, imitatie** <sup>\*</sup> , **spoof**, **phish gefilterd**:</span><span class="sxs-lookup"><span data-stu-id="307e4-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="307e4-333">**DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="307e4-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="307e4-334">**DETECTIE VAN URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-335">**Gefilterde antispam**</span><span class="sxs-lookup"><span data-stu-id="307e4-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="307e4-336">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="307e4-336">**ZAP removed**</span></span>
- <span data-ttu-id="307e4-337">**Detectie door Safe koppelingen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="307e4-338"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="307e4-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="307e4-339">Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="307e4-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="307e4-340">Exporteren vanuit de techweergave</span><span class="sxs-lookup"><span data-stu-id="307e4-340">Export from Tech view</span></span>

<span data-ttu-id="307e4-341">Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="307e4-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="307e4-342">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="307e4-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="307e4-343">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="307e4-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="307e4-344">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="307e4-345">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="307e4-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="307e4-346">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="307e4-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="307e4-347">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="307e4-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Technische weergave in het rapport Mailflow-status](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="307e4-349">Rapport malwaredetecties</span><span class="sxs-lookup"><span data-stu-id="307e4-349">Malware detections report</span></span>

<span data-ttu-id="307e4-350">Het **rapport Malwaredetecties bevat** informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP).</span><span class="sxs-lookup"><span data-stu-id="307e4-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="307e4-351">Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.</span><span class="sxs-lookup"><span data-stu-id="307e4-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="307e4-352">Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.</span><span class="sxs-lookup"><span data-stu-id="307e4-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="307e4-353">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-354">Zoek op **de pagina & samenwerkingsrapporten** malware die **is gedetecteerd in e-mail** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="307e4-355">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="307e4-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Malwaredetecties in e-mailwidget op de pagina E-mail & samenwerkingsrapporten](../../media/malware-detections-widget.png)

<span data-ttu-id="307e4-357">Op de **rapportpagina Malwaredetecties** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="307e4-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="307e4-358">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-359">**Richting:** **Binnenkomende** en **uitgaande**</span><span class="sxs-lookup"><span data-stu-id="307e4-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

<span data-ttu-id="307e4-361">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="307e4-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="307e4-362">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-362">**Date**</span></span>
- <span data-ttu-id="307e4-363">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-363">**Sender address**</span></span>
- <span data-ttu-id="307e4-364">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="307e4-364">**Recipient address**</span></span>
- <span data-ttu-id="307e4-365">**Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="307e4-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="307e4-366">Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).</span><span class="sxs-lookup"><span data-stu-id="307e4-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="307e4-367">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-367">**Subject**</span></span>
- <span data-ttu-id="307e4-368">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="307e4-368">**Filename**</span></span>
- <span data-ttu-id="307e4-369">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="307e4-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="307e4-370">E-maillatentierapport</span><span class="sxs-lookup"><span data-stu-id="307e4-370">Mail latency report</span></span>

<span data-ttu-id="307e4-371">Het **rapport E-maillatentie** in Defender voor Office 365 bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="307e4-372">Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="307e4-373">Rapport over spamdetectie</span><span class="sxs-lookup"><span data-stu-id="307e4-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="307e4-374">Het **rapport Spamdetecties** gaat uiteindelijk weg.</span><span class="sxs-lookup"><span data-stu-id="307e4-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="307e4-375">Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="307e4-376">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="307e4-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="307e4-377">Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="307e4-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="307e4-378">In de oudere versie van het rapport ziet u alleen **Goede e-mail** en **Gevangen als spam.**</span><span class="sxs-lookup"><span data-stu-id="307e4-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="307e4-379">Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing.</span><span class="sxs-lookup"><span data-stu-id="307e4-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="307e4-380">Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="307e4-381">Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.</span><span class="sxs-lookup"><span data-stu-id="307e4-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="307e4-382"><sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="307e4-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="307e4-383">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-384">Zoek op **de pagina & samenwerkingsrapporten** naar **Spoofdetecties** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="307e4-385">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="307e4-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Spoofdetecties op de pagina E-mail & samenwerkingsrapporten](../../media/spoof-detections-widget.png)

<span data-ttu-id="307e4-387">In de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="307e4-387">The chart shows the following information:</span></span>

- <span data-ttu-id="307e4-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="307e4-388">**Pass**</span></span>
- <span data-ttu-id="307e4-389">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="307e4-389">**Fail**</span></span>
- <span data-ttu-id="307e4-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="307e4-390">**SoftPass**</span></span>
- <span data-ttu-id="307e4-391">**Geen**</span><span class="sxs-lookup"><span data-stu-id="307e4-391">**None**</span></span>
- <span data-ttu-id="307e4-392">**Overige**</span><span class="sxs-lookup"><span data-stu-id="307e4-392">**Other**</span></span>

<span data-ttu-id="307e4-393">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.</span><span class="sxs-lookup"><span data-stu-id="307e4-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="307e4-394">Op de **pagina Spoof-e-mailrapport** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="307e4-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="307e4-395">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-396">**Resultaat**:</span><span class="sxs-lookup"><span data-stu-id="307e4-396">**Result**:</span></span>
  - <span data-ttu-id="307e4-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="307e4-397">**Pass**</span></span>
  - <span data-ttu-id="307e4-398">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="307e4-398">**Fail**</span></span>
  - <span data-ttu-id="307e4-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="307e4-399">**SoftPass**</span></span>
  - <span data-ttu-id="307e4-400">**Geen**</span><span class="sxs-lookup"><span data-stu-id="307e4-400">**None**</span></span>
  - <span data-ttu-id="307e4-401">**Overige**</span><span class="sxs-lookup"><span data-stu-id="307e4-401">**Other**</span></span>
- <span data-ttu-id="307e4-402">**Spooftype:** **Intern** en **Extern**</span><span class="sxs-lookup"><span data-stu-id="307e4-402">**Spoof type**: **Internal** and **External**</span></span>

![Pagina spoof-e-mailrapport in de Microsoft 365 Defender portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="307e4-404">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="307e4-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="307e4-405">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-405">**Date**</span></span>
- <span data-ttu-id="307e4-406">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="307e4-406">**Spoofed user**</span></span>
- <span data-ttu-id="307e4-407">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="307e4-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="307e4-408">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="307e4-408">**Spoof type**</span></span>
- <span data-ttu-id="307e4-409">**Result**</span><span class="sxs-lookup"><span data-stu-id="307e4-409">**Result**</span></span>
- <span data-ttu-id="307e4-410">**Resultaatcode**</span><span class="sxs-lookup"><span data-stu-id="307e4-410">**Result code**</span></span>
- <span data-ttu-id="307e4-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="307e4-411">**SPF**</span></span>
- <span data-ttu-id="307e4-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="307e4-412">**DKIM**</span></span>
- <span data-ttu-id="307e4-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="307e4-413">**DMARC**</span></span>
- <span data-ttu-id="307e4-414">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="307e4-414">**Message count**</span></span>

<span data-ttu-id="307e4-415">Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="307e4-416">Rapport Inzendingen</span><span class="sxs-lookup"><span data-stu-id="307e4-416">Submissions report</span></span>

<span data-ttu-id="307e4-417">Het **rapport Inzendingen** bevat informatie over items die beheerders hebben gerapporteerd bij Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="307e4-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="307e4-418">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="307e4-419">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-420">Zoek op **de pagina & samenwerkingsrapporten** naar **Inzendingen** en klik vervolgens op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="307e4-421">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="307e4-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="307e4-422">Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Inzendingen op de pagina E-& samenwerkingsrapporten](../../media/submissions-report-widget.png)

<span data-ttu-id="307e4-424">In de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="307e4-424">The chart shows the following information:</span></span>

- <span data-ttu-id="307e4-425">**In behandeling**</span><span class="sxs-lookup"><span data-stu-id="307e4-425">**Pending**</span></span>
- <span data-ttu-id="307e4-426">**Voltooid**</span><span class="sxs-lookup"><span data-stu-id="307e4-426">**Completed**</span></span>

<span data-ttu-id="307e4-427">Op de **pagina Inzendingen** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="307e4-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="307e4-428">**Datum gerapporteerd:** **Begintijd** en **eindtijd**</span><span class="sxs-lookup"><span data-stu-id="307e4-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="307e4-429">**Inzendingstype**:</span><span class="sxs-lookup"><span data-stu-id="307e4-429">**Submission type**:</span></span>
  - <span data-ttu-id="307e4-430">**E-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-430">**Email**</span></span>
  - <span data-ttu-id="307e4-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="307e4-431">**URL**</span></span>
  - <span data-ttu-id="307e4-432">**Bestand**</span><span class="sxs-lookup"><span data-stu-id="307e4-432">**File**</span></span>
- <span data-ttu-id="307e4-433">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="307e4-433">**Submission ID**</span></span>
- <span data-ttu-id="307e4-434">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="307e4-434">**Network Message ID**</span></span>
- <span data-ttu-id="307e4-435">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-435">**Sender**</span></span>
- <span data-ttu-id="307e4-436">**Naam**</span><span class="sxs-lookup"><span data-stu-id="307e4-436">**Name**</span></span>
- <span data-ttu-id="307e4-437">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="307e4-437">**Submitted by**</span></span>
- <span data-ttu-id="307e4-438">**Reden voor het indienen** van :</span><span class="sxs-lookup"><span data-stu-id="307e4-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="307e4-439">**Geen ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-439">**Not junk**</span></span>
  - <span data-ttu-id="307e4-440">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="307e4-440">**Phish**</span></span>
  - <span data-ttu-id="307e4-441">**Malware**</span><span class="sxs-lookup"><span data-stu-id="307e4-441">**Malware**</span></span>
  - <span data-ttu-id="307e4-442">**Spam**</span><span class="sxs-lookup"><span data-stu-id="307e4-442">**Spam**</span></span>
- <span data-ttu-id="307e4-443">**Status opnieuw scannen:**</span><span class="sxs-lookup"><span data-stu-id="307e4-443">**Rescan status**:</span></span>
  - <span data-ttu-id="307e4-444">**In behandeling**</span><span class="sxs-lookup"><span data-stu-id="307e4-444">**Pending**</span></span>
  - <span data-ttu-id="307e4-445">**Voltooid**</span><span class="sxs-lookup"><span data-stu-id="307e4-445">**Completed**</span></span>

<span data-ttu-id="307e4-446">De detailtabel onder de grafiek bevat dezelfde  informatie en heeft  dezelfde opties voor groepen of kolommen aanpassen als op het tabblad Ingediend voor analyse op  **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="307e4-447">Zie Beheerdersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="307e4-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Rapportpagina Inzendingen in de Microsoft 365 Defender portal](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="307e4-449">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="307e4-449">Threat protection status report</span></span>

<span data-ttu-id="307e4-450">Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Defender voor Office 365; De rapporten bevatten echter verschillende gegevens.</span><span class="sxs-lookup"><span data-stu-id="307e4-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="307e4-451">EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="307e4-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="307e4-452">Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische nul-uursre [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md) [Safe](safe-attachments.md)Bijlagen en functies voor imitatiebeveiliging [in anti-phishingbeleid.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="307e4-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="307e4-453">U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="307e4-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="307e4-454">**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="307e4-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="307e4-455">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-456">Zoek op **de pagina & samenwerkingsrapporten** naar Status van **bedreigingsbeveiliging** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="307e4-457">Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:</span><span class="sxs-lookup"><span data-stu-id="307e4-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="307e4-458">Defender voor Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="307e4-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="307e4-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="307e4-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Statuswidget Bedreigingsbeveiliging op de pagina E-mail & samenwerkingsrapporten](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="307e4-461">Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="307e4-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="307e4-462">Als u op  **Filter klikt** op de rapportpagina bedreigingsstatus, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen beperkt zijn tot 30 dagen).</span><span class="sxs-lookup"><span data-stu-id="307e4-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="307e4-463">Met de detailtabel kunt u 30 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="307e4-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="307e4-464">De beschikbare weergaven worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="307e4-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="307e4-465">Gegevens weergeven op overzicht</span><span class="sxs-lookup"><span data-stu-id="307e4-465">View data by Overview</span></span>

![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="307e4-467">In de **weergave Gegevens weergeven op** overzicht worden de volgende detectiegegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="307e4-468">**E-mailmalware**</span><span class="sxs-lookup"><span data-stu-id="307e4-468">**Email malware**</span></span>
- <span data-ttu-id="307e4-469">**E-mail phish**</span><span class="sxs-lookup"><span data-stu-id="307e4-469">**Email phish**</span></span>
- <span data-ttu-id="307e4-470">**Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="307e4-470">**Content malware**</span></span>

<span data-ttu-id="307e4-471">Er is geen detailtabel beschikbaar onder de grafiek.</span><span class="sxs-lookup"><span data-stu-id="307e4-471">No details table is available below the chart.</span></span>

<span data-ttu-id="307e4-472">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-473">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-474">**Detectie:** **E-mail malware,** **E-mail phish** of **Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="307e4-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="307e4-475">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-476">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-477">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-478">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-478">**Direction**</span></span>
- <span data-ttu-id="307e4-479">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-479">**Domain**</span></span>
- <span data-ttu-id="307e4-480">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-480">**Policy type**</span></span>

<span data-ttu-id="307e4-481">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="307e4-482">Gegevens weergeven op \> e-mail phish en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="307e4-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="307e4-484">In de **weergave Gegevens weergeven per \> e-mail phish** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="307e4-485">**URL-schadelijke reputatie**: Kwaadaardige URL-reputatie die is gegenereerd door Defender voor Office 365 <sup>\*</sup> detonaties in andere Microsoft 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="307e4-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="307e4-486">**Geavanceerd filter:** Phishing-signalen op basis van machine learning.</span><span class="sxs-lookup"><span data-stu-id="307e4-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="307e4-487">**Algemeen filter:** Phishing-signalen op basis van analistregels.</span><span class="sxs-lookup"><span data-stu-id="307e4-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="307e4-488">**Spoof intra-org:** Afzender probeert het domein van de geadresseerde te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="307e4-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="307e4-489">**Extern domein vervalsen:** afzender probeert een ander domein te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="307e4-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="307e4-490">**Spoof DMARC:** DMARC-verificatiefout op berichten.</span><span class="sxs-lookup"><span data-stu-id="307e4-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="307e4-491">**Imitatiemerk:** Imitatie van bekende merken op basis van afzenders.</span><span class="sxs-lookup"><span data-stu-id="307e4-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="307e4-492">**Detectie van gemengde analyse**</span><span class="sxs-lookup"><span data-stu-id="307e4-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="307e4-493">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-493">**File reputation**</span></span>
- <span data-ttu-id="307e4-494">**Vingerafdrukmatching**</span><span class="sxs-lookup"><span data-stu-id="307e4-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="307e4-495">**URL-detonatiereputatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-496">**URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-497">**Imitatiegebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-498">**Imitatiedomein:** imitatie van domeinen die de klant bezit <sup>\*</sup> of definieert.</span><span class="sxs-lookup"><span data-stu-id="307e4-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="307e4-499">**Postvakintelligentie** <sup>\*</sup> imiteren: Imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="307e4-500">**Bestandsdetonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-501">**Campagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="307e4-502">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-503">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-503">**Date**</span></span>
- <span data-ttu-id="307e4-504">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-504">**Subject**</span></span>
- <span data-ttu-id="307e4-505">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-505">**Sender**</span></span>
- <span data-ttu-id="307e4-506">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-506">**Recipients**</span></span>
- <span data-ttu-id="307e4-507">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-507">**Detected by**</span></span>
- <span data-ttu-id="307e4-508">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="307e4-508">**Delivery Status**</span></span>
- <span data-ttu-id="307e4-509">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="307e4-509">**Source of Compromise**</span></span>
- <span data-ttu-id="307e4-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-510">**Tags**</span></span>

<span data-ttu-id="307e4-511">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-512">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-513">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-513">**Detection**</span></span>
- <span data-ttu-id="307e4-514">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-515">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-515">**Direction**</span></span>
- <span data-ttu-id="307e4-516">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-517">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-518">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-518">**Domain**</span></span>
- <span data-ttu-id="307e4-519">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-519">**Policy type**</span></span>
- <span data-ttu-id="307e4-520">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="307e4-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="307e4-521">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-521">**Recipients**</span></span>

<span data-ttu-id="307e4-522">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="307e4-523">Gegevens weergeven op \> e-mailmalware en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="307e4-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="307e4-525">In de **weergave Gegevens weergeven per e-mail \> malware** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="307e4-526">**Bestandsdetonatie** <sup>\*</sup> : Detectie door Safe bijlagen.</span><span class="sxs-lookup"><span data-stu-id="307e4-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="307e4-527">**Reputatie van bestandsdetonatie:** alle schadelijke bestandsreputatie die door Defender wordt gegenereerd <sup>\*</sup> Office 365 detonaties.</span><span class="sxs-lookup"><span data-stu-id="307e4-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="307e4-528">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-528">**File reputation**</span></span>
- <span data-ttu-id="307e4-529">**Anti-malware-engine:** <sup>\*</sup> Detectie van anti-malwareprogramma's.</span><span class="sxs-lookup"><span data-stu-id="307e4-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="307e4-530">**Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="307e4-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="307e4-531">**URL schadelijke reputatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="307e4-532">**URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-532">**URL detonation**</span></span>
- <span data-ttu-id="307e4-533">**URL-detonatiereputatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="307e4-534">**Campagne**</span><span class="sxs-lookup"><span data-stu-id="307e4-534">**Campaign**</span></span>

<span data-ttu-id="307e4-535">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-536">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-536">**Date**</span></span>
- <span data-ttu-id="307e4-537">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-537">**Subject**</span></span>
- <span data-ttu-id="307e4-538">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-538">**Sender**</span></span>
- <span data-ttu-id="307e4-539">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-539">**Recipients**</span></span>
- <span data-ttu-id="307e4-540">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-540">**Detected by**</span></span>
- <span data-ttu-id="307e4-541">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="307e4-541">**Delivery Status**</span></span>
- <span data-ttu-id="307e4-542">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="307e4-542">**Source of Compromise**</span></span>
- <span data-ttu-id="307e4-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-543">**Tags**</span></span>

<span data-ttu-id="307e4-544">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-545">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-546">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-546">**Detection**</span></span>
- <span data-ttu-id="307e4-547">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-548">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-548">**Direction**</span></span>
- <span data-ttu-id="307e4-549">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-550">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-551">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-551">**Domain**</span></span>
- <span data-ttu-id="307e4-552">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-552">**Policy type**</span></span>
- <span data-ttu-id="307e4-553">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="307e4-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="307e4-554">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-554">**Recipients**</span></span>

<span data-ttu-id="307e4-555">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="307e4-556">Grafiekinsplitsing per type beleid en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per e-mail \> malware</span><span class="sxs-lookup"><span data-stu-id="307e4-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave beleidtype voor phishing-e-mail of malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="307e4-558">In de **uitsplitsing Grafiek op type beleid** en Gegevens weergeven per e-mail **\> Phish** of Weergave van gegevens per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="307e4-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="307e4-559">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="307e4-559">**Anti-malware**</span></span>
- <span data-ttu-id="307e4-560">**Safe Bijlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="307e4-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="307e4-561">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="307e4-561">**Anti-phish**</span></span>
- <span data-ttu-id="307e4-562">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="307e4-562">**Anti-spam**</span></span>
- <span data-ttu-id="307e4-563">**E-mailstroomregel** (ook wel transportregel genoemd)</span><span class="sxs-lookup"><span data-stu-id="307e4-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="307e4-564">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="307e4-564">**Others**</span></span>

<span data-ttu-id="307e4-565">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-566">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-566">**Date**</span></span>
- <span data-ttu-id="307e4-567">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-567">**Subject**</span></span>
- <span data-ttu-id="307e4-568">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-568">**Sender**</span></span>
- <span data-ttu-id="307e4-569">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-569">**Recipients**</span></span>
- <span data-ttu-id="307e4-570">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-570">**Detected by**</span></span>
- <span data-ttu-id="307e4-571">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="307e4-571">**Delivery Status**</span></span>
- <span data-ttu-id="307e4-572">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="307e4-572">**Source of Compromise**</span></span>
- <span data-ttu-id="307e4-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-573">**Tags**</span></span>

<span data-ttu-id="307e4-574">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-575">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-576">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-576">**Detection**</span></span>
- <span data-ttu-id="307e4-577">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-578">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-578">**Direction**</span></span>
- <span data-ttu-id="307e4-579">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-580">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-581">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-581">**Domain**</span></span>
- <span data-ttu-id="307e4-582">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-582">**Policy type**</span></span>
- <span data-ttu-id="307e4-583">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="307e4-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="307e4-584">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-584">**Recipients**</span></span>

<span data-ttu-id="307e4-585">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="307e4-586">Grafiekinsplitsing op bezorgingsstatus en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per \> e-mail malware</span><span class="sxs-lookup"><span data-stu-id="307e4-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave bezorgingsstatus voor phishing-e-mail en malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="307e4-588">In de **uitsplitsing Grafiek per bezorgingsstatus** en **Gegevens weergeven per e-mail \> phish** of Gegevens weergeven per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="307e4-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="307e4-589">**Gehost postvak: Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="307e4-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="307e4-590">**Gehost postvak: Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="307e4-591">**Gehost postvak: aangepaste map**</span><span class="sxs-lookup"><span data-stu-id="307e4-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="307e4-592">**Gehost postvak: Verwijderde items**</span><span class="sxs-lookup"><span data-stu-id="307e4-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="307e4-593">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="307e4-593">**Forwarded**</span></span>
- <span data-ttu-id="307e4-594">**On-premises server: geleverd**</span><span class="sxs-lookup"><span data-stu-id="307e4-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="307e4-595">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="307e4-595">**Quarantine**</span></span>
- <span data-ttu-id="307e4-596">**Bezorging mislukt**</span><span class="sxs-lookup"><span data-stu-id="307e4-596">**Delivery failed**</span></span>
- <span data-ttu-id="307e4-597">**Laten vallen**</span><span class="sxs-lookup"><span data-stu-id="307e4-597">**Dropped**</span></span>

<span data-ttu-id="307e4-598">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-599">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-599">**Date**</span></span>
- <span data-ttu-id="307e4-600">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-600">**Subject**</span></span>
- <span data-ttu-id="307e4-601">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-601">**Sender**</span></span>
- <span data-ttu-id="307e4-602">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-602">**Recipients**</span></span>
- <span data-ttu-id="307e4-603">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-603">**Detected by**</span></span>
- <span data-ttu-id="307e4-604">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="307e4-604">**Delivery Status**</span></span>
- <span data-ttu-id="307e4-605">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="307e4-605">**Source of Compromise**</span></span>
- <span data-ttu-id="307e4-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-606">**Tags**</span></span>

<span data-ttu-id="307e4-607">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-608">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-609">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-609">**Detection**</span></span>
- <span data-ttu-id="307e4-610">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-611">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-611">**Direction**</span></span>
- <span data-ttu-id="307e4-612">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-613">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-614">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-614">**Domain**</span></span>
- <span data-ttu-id="307e4-615">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-615">**Policy type**</span></span>
- <span data-ttu-id="307e4-616">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="307e4-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="307e4-617">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-617">**Recipients**</span></span>

<span data-ttu-id="307e4-618">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="307e4-619">Gegevens weergeven op \> inhoudsmalware</span><span class="sxs-lookup"><span data-stu-id="307e4-619">View data by Content \> Malware</span></span>

![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="307e4-621">In de **weergave Gegevens weergeven op \> inhoudsmalware** worden de volgende gegevens weergegeven in de grafiek voor Microsoft Defender voor Office 365 organisaties:</span><span class="sxs-lookup"><span data-stu-id="307e4-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="307e4-622">**Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="307e4-623">**Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="307e4-624">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-625">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-626">**Locatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-626">**Location**</span></span>
- <span data-ttu-id="307e4-627">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-627">**Detected by**</span></span>
- <span data-ttu-id="307e4-628">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="307e4-628">**Malware name**</span></span>

<span data-ttu-id="307e4-629">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-630">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-631">**Detectie:** **Anti-malware-engine** of **Bestandsdetonatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="307e4-632">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="307e4-633">Gegevens weergeven op systeem overschrijven</span><span class="sxs-lookup"><span data-stu-id="307e4-633">View data by System override</span></span>

![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="307e4-635">In de **weergave Gegevens weergeven op systeem overschrijven** worden de volgende redengegevens overschrijven weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="307e4-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="307e4-636">**On-premises overslaan**</span><span class="sxs-lookup"><span data-stu-id="307e4-636">**On-premises skip**</span></span>
- <span data-ttu-id="307e4-637">**IP-toestaan**</span><span class="sxs-lookup"><span data-stu-id="307e4-637">**IP allow**</span></span>
- <span data-ttu-id="307e4-638">**Exchange regel voor e-mailtransport** (regel e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="307e4-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="307e4-639">**Organisatie toegestaan afzenders**</span><span class="sxs-lookup"><span data-stu-id="307e4-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="307e4-640">**Toegestane domeinen van de organisatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="307e4-641">**ZAP niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="307e4-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="307e4-642">**Map Ongewenste e-mail niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="307e4-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="307e4-643">**Gebruiker Safe afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-643">**User Safe Sender**</span></span>
- <span data-ttu-id="307e4-644">**User Safe Domain**</span><span class="sxs-lookup"><span data-stu-id="307e4-644">**User Safe Domain**</span></span>

<span data-ttu-id="307e4-645">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="307e4-646">**Datum**</span><span class="sxs-lookup"><span data-stu-id="307e4-646">**Date**</span></span>
- <span data-ttu-id="307e4-647">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-647">**Subject**</span></span>
- <span data-ttu-id="307e4-648">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-648">**Sender**</span></span>
- <span data-ttu-id="307e4-649">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-649">**Recipients**</span></span>
- <span data-ttu-id="307e4-650">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-650">**Detected by**</span></span>
- <span data-ttu-id="307e4-651">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="307e4-651">**Delivery Status**</span></span>
- <span data-ttu-id="307e4-652">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="307e4-652">**Source of Compromise**</span></span>
- <span data-ttu-id="307e4-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-653">**Tags**</span></span>

<span data-ttu-id="307e4-654">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="307e4-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="307e4-655">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="307e4-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="307e4-656">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="307e4-656">**Detection**</span></span>
- <span data-ttu-id="307e4-657">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="307e4-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="307e4-658">**Richting**</span><span class="sxs-lookup"><span data-stu-id="307e4-658">**Direction**</span></span>
- <span data-ttu-id="307e4-659">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="307e4-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="307e4-660">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="307e4-661">**Domein**</span><span class="sxs-lookup"><span data-stu-id="307e4-661">**Domain**</span></span>
- <span data-ttu-id="307e4-662">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="307e4-662">**Policy type**</span></span>
- <span data-ttu-id="307e4-663">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="307e4-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="307e4-664">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="307e4-664">**Recipients**</span></span>

<span data-ttu-id="307e4-665">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="307e4-666"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="307e4-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="307e4-667">Top malwarerapport</span><span class="sxs-lookup"><span data-stu-id="307e4-667">Top malware report</span></span>

<span data-ttu-id="307e4-668">Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="307e4-669">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-670">Zoek op **de pagina & samenwerkingsrapporten** naar **Top malware** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="307e4-671">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="307e4-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Top malware widget on the Email & collaboration reports page](../../media/top-malware-report-widget.png)

<span data-ttu-id="307e4-673">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="307e4-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="307e4-674">Op de **pagina Top malwarerapport** wordt een grotere versie van het cirkeldiagram weergegeven op de rapportpagina. In de detailtabel onder de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="307e4-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="307e4-675">**Top malware**</span><span class="sxs-lookup"><span data-stu-id="307e4-675">**Top malware**</span></span>
- <span data-ttu-id="307e4-676">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="307e4-676">**Count**</span></span>

<span data-ttu-id="307e4-677">Als u op **Filter klikt,** kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="307e4-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="307e4-679">URL-bedreigingsbeveiligingsrapport</span><span class="sxs-lookup"><span data-stu-id="307e4-679">URL threat protection report</span></span>

<span data-ttu-id="307e4-680">Het **rapport URL-bedreigingsbeveiliging** is alleen beschikbaar in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="307e4-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="307e4-681">Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="307e4-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="307e4-682">Rapport met gerapporteerde berichten van gebruiker</span><span class="sxs-lookup"><span data-stu-id="307e4-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="307e4-683">Als het rapport **Gerapporteerde** berichten van de gebruiker correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="307e4-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="307e4-684">Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="307e4-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="307e4-685">Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="307e4-686">Het **rapport Gerapporteerde** berichten van gebruiker bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoeging Rapportbericht of de invoeging [Phishing melden.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="307e4-687">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="307e4-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="307e4-688">Zoek op **de pagina E-& samenwerkingsrapporten** naar **Gerapporteerde** berichten van de gebruiker en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="307e4-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="307e4-689">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="307e4-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="307e4-690">Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget met gerapporteerde berichten van gebruiker op de pagina E-mail & samenwerkingsrapporten](../../media/user-reported-messages-widget.png)

<span data-ttu-id="307e4-692">Op de **pagina Gerapporteerde** berichten van gebruiker kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="307e4-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="307e4-693">**Datum gerapporteerd:** **Begintijd** en **eindtijd**</span><span class="sxs-lookup"><span data-stu-id="307e4-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="307e4-694">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-694">**Reported by**</span></span>
- <span data-ttu-id="307e4-695">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-695">**Email subject**</span></span>
- <span data-ttu-id="307e4-696">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="307e4-696">**Message reported ID**</span></span>
- <span data-ttu-id="307e4-697">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="307e4-697">**Network Message ID**</span></span>
- <span data-ttu-id="307e4-698">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-698">**Sender**</span></span>
- <span data-ttu-id="307e4-699">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="307e4-699">**Reported reason**</span></span>
  - <span data-ttu-id="307e4-700">**Geen ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="307e4-700">**Not junk**</span></span>
  - <span data-ttu-id="307e4-701">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="307e4-701">**Phish**</span></span>
  - <span data-ttu-id="307e4-702">**Spam**</span><span class="sxs-lookup"><span data-stu-id="307e4-702">**Spam**</span></span>
- <span data-ttu-id="307e4-703">**Phish-simulatie:** **Ja** of **Nee**</span><span class="sxs-lookup"><span data-stu-id="307e4-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="307e4-704">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="307e4-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="307e4-705">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="307e4-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="307e4-706">**Geen**</span><span class="sxs-lookup"><span data-stu-id="307e4-706">**None**</span></span>
- <span data-ttu-id="307e4-707">**Reden**</span><span class="sxs-lookup"><span data-stu-id="307e4-707">**Reason**</span></span>
- <span data-ttu-id="307e4-708">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-708">**Sender**</span></span>
- <span data-ttu-id="307e4-709">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-709">**Reported by**</span></span>
- <span data-ttu-id="307e4-710">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="307e4-710">**Rescan result**</span></span>
- <span data-ttu-id="307e4-711">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="307e4-711">**Phish simulation**</span></span>

![Rapport met gerapporteerde berichten van gebruiker](../../media/user-reported-messages-report.png)

<span data-ttu-id="307e4-713">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="307e4-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="307e4-714">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="307e4-714">**Email subject**</span></span>
- <span data-ttu-id="307e4-715">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="307e4-715">**Reported by**</span></span>
- <span data-ttu-id="307e4-716">**Datum gerapporteerd**</span><span class="sxs-lookup"><span data-stu-id="307e4-716">**Date reported**</span></span>
- <span data-ttu-id="307e4-717">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="307e4-717">**Sender**</span></span>
- <span data-ttu-id="307e4-718">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="307e4-718">**Reported reason**</span></span>
- <span data-ttu-id="307e4-719">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="307e4-719">**Rescan result**</span></span>
- <span data-ttu-id="307e4-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="307e4-720">**Tags**</span></span>

<span data-ttu-id="307e4-721">Als u een bericht wilt verzenden naar Microsoft voor analyse, selecteert u de berichtinvoer in de tabel, klikt u op Verzenden bij **Microsoft** voor analyse en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="307e4-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="307e4-722">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="307e4-722">**Report clean**</span></span>
- <span data-ttu-id="307e4-723">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="307e4-723">**Report phishing**</span></span>
- <span data-ttu-id="307e4-724">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="307e4-724">**Report malware**</span></span>
- <span data-ttu-id="307e4-725">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="307e4-725">**Report spam**'</span></span>
- <span data-ttu-id="307e4-726">**Onderzoek starten** (Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="307e4-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="307e4-727">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="307e4-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="307e4-728">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="307e4-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="307e4-729">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="307e4-729">**Organization Management**</span></span>
- <span data-ttu-id="307e4-730">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="307e4-730">**Security Administrator**</span></span>
- <span data-ttu-id="307e4-731">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="307e4-731">**Security Reader**</span></span>
- <span data-ttu-id="307e4-732">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="307e4-732">**Global Reader**</span></span>

<span data-ttu-id="307e4-733">Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="307e4-734">**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="307e4-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="307e4-735">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="307e4-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="307e4-736">Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?</span><span class="sxs-lookup"><span data-stu-id="307e4-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="307e4-737">Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="307e4-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="307e4-738">Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="307e4-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="307e4-739">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="307e4-739">Related topics</span></span>

[<span data-ttu-id="307e4-740">Bescherming tegen spam en anti-malware in EOP</span><span class="sxs-lookup"><span data-stu-id="307e4-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="307e4-741">Slimme rapporten en inzichten in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="307e4-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="307e4-742">E-mailstroomrapporten weergeven in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="307e4-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="307e4-743">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="307e4-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
