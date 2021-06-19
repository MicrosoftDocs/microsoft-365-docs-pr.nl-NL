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
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022911"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="b3318-103">E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="b3318-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b3318-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b3318-104">**Applies to**</span></span>
- [<span data-ttu-id="b3318-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b3318-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b3318-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3318-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b3318-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3318-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b3318-108">Er zijn diverse rapporten beschikbaar in de Microsoft 365 Defender-portal om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie <https://security.microsoft.com> beschermen.</span><span class="sxs-lookup"><span data-stu-id="b3318-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="b3318-109">Als u de benodigde machtigingen [hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken  in de Microsoft 365 Defender-portal door naar Rapporten E-mail & samenwerking e-mail \>  \> **& samenwerkingsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="b3318-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-110">Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="b3318-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender-portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="b3318-112">Voor sommige rapporten op de pagina **E-& samenwerkingsrapporten** is Microsoft Defender voor Office 365 vereist.</span><span class="sxs-lookup"><span data-stu-id="b3318-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b3318-113">Zie Defender voor [Office 365-rapporten weergeven in de Microsoft 365 Defender-portal](view-reports-for-mdo.md)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="b3318-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="b3318-114">Rapporten die zijn gerelateerd aan e-mailstroom, zijn nu in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="b3318-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="b3318-115">Zie E-mailstroomrapporten in het [nieuwe Exchange-beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="b3318-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="b3318-116">Rapport over gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="b3318-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="b3318-117">Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="b3318-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="b3318-118">Het is niet beschikbaar in zelfstandige EOP-organisaties (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="b3318-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="b3318-119">In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt.</span><span class="sxs-lookup"><span data-stu-id="b3318-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="b3318-120">Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="b3318-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="b3318-121">Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts.</span><span class="sxs-lookup"><span data-stu-id="b3318-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="b3318-122">Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Voor gecompromitteerde gebruikers op de pagina E-mail & samenwerkingsrapporten](../../media/compromised-users-report-widget.png)

<span data-ttu-id="b3318-124">De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="b3318-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="b3318-125">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-126">Zoek op **de pagina & samenwerkingsrapporten** naar Gecompromitteerde **gebruikers** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="b3318-127">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="b3318-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="b3318-128">Op de pagina Gecompromitteerd gebruikers kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven: </span><span class="sxs-lookup"><span data-stu-id="b3318-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b3318-129">**Datum (UTC)**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="b3318-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="b3318-130">**Activiteit**:</span><span class="sxs-lookup"><span data-stu-id="b3318-130">**Activity**:</span></span>
  - <span data-ttu-id="b3318-131">**Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="b3318-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="b3318-132">**Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.</span><span class="sxs-lookup"><span data-stu-id="b3318-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="b3318-133">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="b3318-135">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="b3318-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b3318-136">**Aanmaaktijd**</span><span class="sxs-lookup"><span data-stu-id="b3318-136">**Creation time**</span></span>
- <span data-ttu-id="b3318-137">**Gebruikers-id**</span><span class="sxs-lookup"><span data-stu-id="b3318-137">**User ID**</span></span>
- <span data-ttu-id="b3318-138">**Actie**</span><span class="sxs-lookup"><span data-stu-id="b3318-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="b3318-139">Rapport met exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="b3318-139">Exchange transport rule report</span></span>

<span data-ttu-id="b3318-140">Het **rapport Exchange-transportregel** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="b3318-141">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-142">Zoek op **de pagina E-& samenwerkingsrapporten** **naar Exchange-transportregel** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="b3318-143">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="b3318-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-transportregelwidget op de pagina E-mail & samenwerkingsrapporten](../../media/transport-rule-report-widget.png)

<span data-ttu-id="b3318-145">Op de rapportpagina van de **Exchange-transportregel** worden de beschikbare grafieken en gegevens in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="b3318-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="b3318-146">Grafiek uitsplitsing op richting</span><span class="sxs-lookup"><span data-stu-id="b3318-146">Chart breakdown by Direction</span></span>

![Richtingsweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="b3318-148">Als u Grafiek **uitsplitsing op richting selecteert,** zijn de volgende grafieken beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="b3318-149">**Gegevens weergeven op exchange-transportregels:** het  aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="b3318-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="b3318-150">**Gegevens weergeven op DLP Exchange-transportregels:**  het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door DLP-regels (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="b3318-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="b3318-151">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b3318-152">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-152">**Date**</span></span>
- <span data-ttu-id="b3318-153">**DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**</span><span class="sxs-lookup"><span data-stu-id="b3318-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="b3318-154">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="b3318-154">**Transport rule**</span></span>
- <span data-ttu-id="b3318-155">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-155">**Subject**</span></span>
- <span data-ttu-id="b3318-156">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-156">**Sender address**</span></span>
- <span data-ttu-id="b3318-157">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="b3318-157">**Recipient address**</span></span>
- <span data-ttu-id="b3318-158">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="b3318-158">**Severity**</span></span>
- <span data-ttu-id="b3318-159">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-159">**Direction**</span></span>

<span data-ttu-id="b3318-160">U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b3318-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b3318-161">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-162">**Richting:** **Uitgaande en Inkomende** </span><span class="sxs-lookup"><span data-stu-id="b3318-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="b3318-163">**Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**</span><span class="sxs-lookup"><span data-stu-id="b3318-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="b3318-164">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="b3318-165">Uitsplitsing van grafieken op ernst</span><span class="sxs-lookup"><span data-stu-id="b3318-165">Chart breakdown by Severity</span></span>

![Ernstweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="b3318-167">Als u Grafiek **uitsplitsing op ernst selecteert,** zijn de volgende grafieken beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="b3318-168">**Gegevens weergeven op exchange-transportregels:** het aantal berichten met hoge **ernst,** gemiddelde **ernst** en **berichten met lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="b3318-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="b3318-169">U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="b3318-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="b3318-170">Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="b3318-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="b3318-171">**Gegevens weergeven op DLP Exchange-transportregels:** het aantal berichten  met hoge **ernst,** gemiddelde ernst en lage ernst die zijn beïnvloed door DLP-regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="b3318-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="b3318-172">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b3318-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-173">**Date**</span></span>
- <span data-ttu-id="b3318-174">**DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**</span><span class="sxs-lookup"><span data-stu-id="b3318-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="b3318-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="b3318-175">**Transport rule**</span></span>
- <span data-ttu-id="b3318-176">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-176">**Subject**</span></span>
- <span data-ttu-id="b3318-177">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-177">**Sender address**</span></span>
- <span data-ttu-id="b3318-178">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="b3318-178">**Recipient address**</span></span>
- <span data-ttu-id="b3318-179">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="b3318-179">**Severity**</span></span>
- <span data-ttu-id="b3318-180">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-180">**Direction**</span></span>

<span data-ttu-id="b3318-181">U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b3318-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b3318-182">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-183">**Richting:** **Uitgaande en Inkomende** </span><span class="sxs-lookup"><span data-stu-id="b3318-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="b3318-184">**Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**</span><span class="sxs-lookup"><span data-stu-id="b3318-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="b3318-185">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="b3318-186">Doorsturen van rapport</span><span class="sxs-lookup"><span data-stu-id="b3318-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="b3318-187">Het **rapport Doorsturen** is nu beschikbaar in het EAC.</span><span class="sxs-lookup"><span data-stu-id="b3318-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="b3318-188">Zie Rapport Automatisch doorgestuurde berichten in het nieuwe EAC voor [meer informatie.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b3318-189">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="b3318-189">Mailflow status report</span></span>

<span data-ttu-id="b3318-190">Het **mailflowstatusrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, spamdetecties, malware, e-mail die als 'goed' is geïdentificeerd en informatie over e-mail die is toegestaan of geblokkeerd op de rand.</span><span class="sxs-lookup"><span data-stu-id="b3318-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="b3318-191">Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat e-mail wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="b3318-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b3318-192">Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="b3318-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b3318-193">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-194">Zoek op **de & e-mail met samenwerkingsrapporten** de **statusoverzicht van Mailflow** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="b3318-195">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="b3318-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Overzichtswidget Mailflow-status op de pagina E-mail & samenwerkingsrapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="b3318-197">Typweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="b3318-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="b3318-198">Wanneer u het rapport opent, is **het tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b3318-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="b3318-199">Deze weergave bevat standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="b3318-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b3318-200">**Datum (UTC)** De afgelopen 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="b3318-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="b3318-201">**E-mailrichting**:</span><span class="sxs-lookup"><span data-stu-id="b3318-201">**Mail direction**:</span></span>
  - <span data-ttu-id="b3318-202">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="b3318-202">**Inbound**</span></span>
  - <span data-ttu-id="b3318-203">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="b3318-203">**Outbound**</span></span>
  - <span data-ttu-id="b3318-204">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="b3318-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b3318-205">afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="b3318-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="b3318-206">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="b3318-206">**Type**:</span></span>
  - <span data-ttu-id="b3318-207">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-207">**Good mail**</span></span>
  - <span data-ttu-id="b3318-208">**Malware**</span><span class="sxs-lookup"><span data-stu-id="b3318-208">**Malware**</span></span>
  - <span data-ttu-id="b3318-209">**Spam**</span><span class="sxs-lookup"><span data-stu-id="b3318-209">**Spam**</span></span>
  - <span data-ttu-id="b3318-210">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="b3318-210">**Edge protection**</span></span>
  - <span data-ttu-id="b3318-211">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="b3318-211">**Rule messages**</span></span>
  - <span data-ttu-id="b3318-212">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-212">**Phishing email**</span></span>
- <span data-ttu-id="b3318-213">**Domein:** **Alles**</span><span class="sxs-lookup"><span data-stu-id="b3318-213">**Domain**: **All**</span></span>

<span data-ttu-id="b3318-214">De grafiek wordt ingedeeld op basis van **de waarden Type.**</span><span class="sxs-lookup"><span data-stu-id="b3318-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="b3318-215">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="b3318-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="b3318-216">De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="b3318-217">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-217">**Direction**</span></span>
- <span data-ttu-id="b3318-218">**Type**</span><span class="sxs-lookup"><span data-stu-id="b3318-218">**Type**</span></span>
- <span data-ttu-id="b3318-219">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="b3318-219">**24 hours**</span></span>
- <span data-ttu-id="b3318-220">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="b3318-220">**3 days**</span></span>
- <span data-ttu-id="b3318-221">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="b3318-221">**7 days**</span></span>
- <span data-ttu-id="b3318-222">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="b3318-222">**15 days**</span></span>
- <span data-ttu-id="b3318-223">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="b3318-223">**30 days**</span></span>

<span data-ttu-id="b3318-224">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="b3318-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="b3318-225">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b3318-226">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="b3318-227">**Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="b3318-228">**Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="b3318-229">Exporteren vanuit de weergave Type</span><span class="sxs-lookup"><span data-stu-id="b3318-229">Export from Type view</span></span>

<span data-ttu-id="b3318-230">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="b3318-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b3318-231">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b3318-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b3318-232">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="b3318-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b3318-233">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b3318-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Weergave typen in het rapport Mailflow-status](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="b3318-235">Richtingsweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="b3318-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="b3318-236">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3318-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="b3318-237">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="b3318-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="b3318-238">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="b3318-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b3318-239">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3318-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b3318-240">De detailtabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="b3318-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="b3318-241">De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.</span><span class="sxs-lookup"><span data-stu-id="b3318-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="b3318-242">Exporteren vanuit de richtingsweergave</span><span class="sxs-lookup"><span data-stu-id="b3318-242">Export from Direction view</span></span>

<span data-ttu-id="b3318-243">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="b3318-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="b3318-244">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b3318-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="b3318-245">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="b3318-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b3318-246">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b3318-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtingsweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="b3318-248">Trechterweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="b3318-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="b3318-249">In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="b3318-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="b3318-250">Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="b3318-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="b3318-251">Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="b3318-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b3318-252">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="b3318-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b3318-253">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="b3318-253">**Direction**:</span></span>
  - <span data-ttu-id="b3318-254">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="b3318-254">**Inbound**</span></span>
  - <span data-ttu-id="b3318-255">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="b3318-255">**Outbound**</span></span>
  - <span data-ttu-id="b3318-256">**Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).</span><span class="sxs-lookup"><span data-stu-id="b3318-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="b3318-257">De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="b3318-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b3318-258">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="b3318-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b3318-259">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3318-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b3318-260">In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="b3318-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="b3318-261">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-261">**Total email**</span></span>
- <span data-ttu-id="b3318-262">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="b3318-262">**Email after edge protection**</span></span>
- <span data-ttu-id="b3318-263">**Regel E-mail na transport** (regel voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="b3318-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="b3318-264">**E-mail na anti-malware, bestandsreputatie, bestandstypeblok**</span><span class="sxs-lookup"><span data-stu-id="b3318-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="b3318-265">**E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="b3318-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="b3318-266">**E-mail na antispam, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="b3318-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="b3318-267">**E-mail na gebruikers- en domein-imitatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-268">**E-mail na bestand en URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-269">**E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="b3318-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="b3318-270"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="b3318-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b3318-271">Als u het e-mailbericht wilt weergeven dat is gefilterd op EOP of Defender Office 365 afzonderlijk, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="b3318-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="b3318-272">De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="b3318-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b3318-273">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-273">**Date**</span></span>
- <span data-ttu-id="b3318-274">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-274">**Total email**</span></span>
- <span data-ttu-id="b3318-275">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="b3318-275">**Edge protection**</span></span>
- <span data-ttu-id="b3318-276">**Anti-malware, bestandsreputatie, bestandstypeblok:**</span><span class="sxs-lookup"><span data-stu-id="b3318-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="b3318-277">**Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="b3318-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="b3318-278">**Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="b3318-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b3318-279">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="b3318-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="b3318-280">**URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="b3318-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="b3318-281">**Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.</span><span class="sxs-lookup"><span data-stu-id="b3318-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="b3318-282">**Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.</span><span class="sxs-lookup"><span data-stu-id="b3318-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="b3318-283">**Antispam, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="b3318-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="b3318-284">**Bulkmailfilters:** Berichten gefilterd op basis van de drempel voor bulksgewijs klagen (BCL) in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="b3318-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="b3318-285">**Gebruikers- en domein-imitatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b3318-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b3318-286">**Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="b3318-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="b3318-287">**Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="b3318-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="b3318-288">**Bestands- en URL-detonatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="b3318-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="b3318-289">**Bestandsdetonatie:** Berichten gefilterd op een Safe bijlagenbeleid.</span><span class="sxs-lookup"><span data-stu-id="b3318-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="b3318-290">**URL-detonatie:** bericht gefilterd door een Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="b3318-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="b3318-291">**Bescherming na bezorging en ZAP (ATP) of ZAP (EOP)**: Automatische purge (ZAP) van nul uur voor malware, spam en phishing.</span><span class="sxs-lookup"><span data-stu-id="b3318-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="b3318-292">Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="b3318-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="b3318-293">Exporteren vanuit de trechterweergave</span><span class="sxs-lookup"><span data-stu-id="b3318-293">Export from Funnel view</span></span>

<span data-ttu-id="b3318-294">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="b3318-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="b3318-295">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="b3318-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b3318-296">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="b3318-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b3318-297">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b3318-298">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="b3318-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b3318-299">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="b3318-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b3318-300">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b3318-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trechterweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="b3318-302">Technische weergave voor het mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="b3318-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="b3318-303">De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="b3318-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="b3318-304">In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="b3318-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="b3318-305">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="b3318-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="b3318-306">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="b3318-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="b3318-307">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="b3318-307">**Direction**:</span></span>
  - <span data-ttu-id="b3318-308">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="b3318-308">**Inbound**</span></span>
  - <span data-ttu-id="b3318-309">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="b3318-309">**Outbound**</span></span>
  - <span data-ttu-id="b3318-310">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="b3318-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="b3318-311">afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)</span><span class="sxs-lookup"><span data-stu-id="b3318-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="b3318-312">De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="b3318-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="b3318-313">U kunt deze filters wijzigen door op Filter te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="b3318-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="b3318-314">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b3318-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="b3318-315">In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="b3318-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="b3318-316">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-316">**Total email**</span></span>
- <span data-ttu-id="b3318-317">**Rand toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="b3318-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="b3318-318">**Transportregel toestaan** en **Transportregel gefilterd** (regels voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="b3318-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="b3318-319">**Geen malware,** **Safe detectie van** bijlagen en detectie van <sup>\*</sup> **anti-malware-engine**</span><span class="sxs-lookup"><span data-stu-id="b3318-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="b3318-320">**Geen phish,** **DMARC-fout,** **imitatiedetectie,** <sup>\*</sup> **spoofdetectie** en **Phish-detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="b3318-321">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-322">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="b3318-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="b3318-323">**Niet-schadelijke e-mail,** **Safe koppelingendetectie** <sup>\*</sup> en **ZAP**</span><span class="sxs-lookup"><span data-stu-id="b3318-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="b3318-324"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3318-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b3318-325">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.</span><span class="sxs-lookup"><span data-stu-id="b3318-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="b3318-326">De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="b3318-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="b3318-327">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="b3318-327">**Date (UTC)**</span></span>
- <span data-ttu-id="b3318-328">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-328">**Total email**</span></span>
- <span data-ttu-id="b3318-329">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="b3318-329">**Edge filtered**</span></span>
- <span data-ttu-id="b3318-330">**Regelberichten:** Berichten die zijn gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="b3318-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="b3318-331">**Anti-malware engine**, **Safe Bijlagen:** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="b3318-332">**DMARC, imitatie** <sup>\*</sup> , **spoof**, **phish gefilterd**:</span><span class="sxs-lookup"><span data-stu-id="b3318-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="b3318-333">**DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="b3318-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="b3318-334">**DETECTIE VAN URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-335">**Gefilterde antispam**</span><span class="sxs-lookup"><span data-stu-id="b3318-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="b3318-336">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="b3318-336">**ZAP removed**</span></span>
- <span data-ttu-id="b3318-337">**Detectie door Safe koppelingen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="b3318-338"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3318-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="b3318-339">Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="b3318-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="b3318-340">Exporteren vanuit de techweergave</span><span class="sxs-lookup"><span data-stu-id="b3318-340">Export from Tech view</span></span>

<span data-ttu-id="b3318-341">Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="b3318-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="b3318-342">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="b3318-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="b3318-343">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="b3318-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="b3318-344">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="b3318-345">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="b3318-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="b3318-346">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="b3318-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="b3318-347">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b3318-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Technische weergave in het rapport Mailflow-status](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="b3318-349">Rapport malwaredetecties</span><span class="sxs-lookup"><span data-stu-id="b3318-349">Malware detections report</span></span>

<span data-ttu-id="b3318-350">Het **rapport Malwaredetecties bevat** informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP).</span><span class="sxs-lookup"><span data-stu-id="b3318-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="b3318-351">Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.</span><span class="sxs-lookup"><span data-stu-id="b3318-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b3318-352">Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.</span><span class="sxs-lookup"><span data-stu-id="b3318-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="b3318-353">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-354">Zoek op **de pagina & samenwerkingsrapporten** malware die **is gedetecteerd in e-mail** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="b3318-355">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="b3318-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Malwaredetecties in e-mailwidget op de pagina E-mail & samenwerkingsrapporten](../../media/malware-detections-widget.png)

<span data-ttu-id="b3318-357">Op de **rapportpagina Malwaredetecties** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="b3318-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="b3318-358">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-359">**Richting:** **Binnenkomende** en **uitgaande**</span><span class="sxs-lookup"><span data-stu-id="b3318-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

<span data-ttu-id="b3318-361">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="b3318-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b3318-362">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-362">**Date**</span></span>
- <span data-ttu-id="b3318-363">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-363">**Sender address**</span></span>
- <span data-ttu-id="b3318-364">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="b3318-364">**Recipient address**</span></span>
- <span data-ttu-id="b3318-365">**Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="b3318-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="b3318-366">Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).</span><span class="sxs-lookup"><span data-stu-id="b3318-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="b3318-367">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-367">**Subject**</span></span>
- <span data-ttu-id="b3318-368">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="b3318-368">**Filename**</span></span>
- <span data-ttu-id="b3318-369">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="b3318-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b3318-370">E-maillatentierapport</span><span class="sxs-lookup"><span data-stu-id="b3318-370">Mail latency report</span></span>

<span data-ttu-id="b3318-371">Het **rapport E-maillatentie** in Defender voor Office 365 bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b3318-372">Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="b3318-373">Rapport over spamdetectie</span><span class="sxs-lookup"><span data-stu-id="b3318-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="b3318-374">Het **rapport Spamdetecties** gaat uiteindelijk weg.</span><span class="sxs-lookup"><span data-stu-id="b3318-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="b3318-375">Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="b3318-376">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="b3318-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="b3318-377">Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="b3318-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="b3318-378">In de oudere versie van het rapport ziet u alleen **Goede e-mail** en **Gevangen als spam.**</span><span class="sxs-lookup"><span data-stu-id="b3318-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="b3318-379">Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing.</span><span class="sxs-lookup"><span data-stu-id="b3318-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="b3318-380">Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b3318-381">Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.</span><span class="sxs-lookup"><span data-stu-id="b3318-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="b3318-382"><sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b3318-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="b3318-383">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-384">Zoek op **de pagina & samenwerkingsrapporten** naar **Spoofdetecties** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="b3318-385">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="b3318-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Spoofdetecties op de pagina E-mail & samenwerkingsrapporten](../../media/spoof-detections-widget.png)

<span data-ttu-id="b3318-387">In de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b3318-387">The chart shows the following information:</span></span>

- <span data-ttu-id="b3318-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="b3318-388">**Pass**</span></span>
- <span data-ttu-id="b3318-389">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="b3318-389">**Fail**</span></span>
- <span data-ttu-id="b3318-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="b3318-390">**SoftPass**</span></span>
- <span data-ttu-id="b3318-391">**Geen**</span><span class="sxs-lookup"><span data-stu-id="b3318-391">**None**</span></span>
- <span data-ttu-id="b3318-392">**Overige**</span><span class="sxs-lookup"><span data-stu-id="b3318-392">**Other**</span></span>

<span data-ttu-id="b3318-393">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.</span><span class="sxs-lookup"><span data-stu-id="b3318-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="b3318-394">Op de **pagina Spoof-e-mailrapport** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="b3318-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b3318-395">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-396">**Resultaat**:</span><span class="sxs-lookup"><span data-stu-id="b3318-396">**Result**:</span></span>
  - <span data-ttu-id="b3318-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="b3318-397">**Pass**</span></span>
  - <span data-ttu-id="b3318-398">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="b3318-398">**Fail**</span></span>
  - <span data-ttu-id="b3318-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="b3318-399">**SoftPass**</span></span>
  - <span data-ttu-id="b3318-400">**Geen**</span><span class="sxs-lookup"><span data-stu-id="b3318-400">**None**</span></span>
  - <span data-ttu-id="b3318-401">**Overige**</span><span class="sxs-lookup"><span data-stu-id="b3318-401">**Other**</span></span>
- <span data-ttu-id="b3318-402">**Spooftype:** **Intern** en **Extern**</span><span class="sxs-lookup"><span data-stu-id="b3318-402">**Spoof type**: **Internal** and **External**</span></span>

![Pagina spoof-e-mailrapport in de Microsoft 365 Defender portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="b3318-404">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="b3318-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b3318-405">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-405">**Date**</span></span>
- <span data-ttu-id="b3318-406">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="b3318-406">**Spoofed user**</span></span>
- <span data-ttu-id="b3318-407">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="b3318-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="b3318-408">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="b3318-408">**Spoof type**</span></span>
- <span data-ttu-id="b3318-409">**Result**</span><span class="sxs-lookup"><span data-stu-id="b3318-409">**Result**</span></span>
- <span data-ttu-id="b3318-410">**Resultaatcode**</span><span class="sxs-lookup"><span data-stu-id="b3318-410">**Result code**</span></span>
- <span data-ttu-id="b3318-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="b3318-411">**SPF**</span></span>
- <span data-ttu-id="b3318-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="b3318-412">**DKIM**</span></span>
- <span data-ttu-id="b3318-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="b3318-413">**DMARC**</span></span>
- <span data-ttu-id="b3318-414">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="b3318-414">**Message count**</span></span>

<span data-ttu-id="b3318-415">Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="b3318-416">Rapport Inzendingen</span><span class="sxs-lookup"><span data-stu-id="b3318-416">Submissions report</span></span>

<span data-ttu-id="b3318-417">Het **rapport Inzendingen** bevat informatie over items die beheerders hebben gerapporteerd bij Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="b3318-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="b3318-418">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="b3318-419">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-420">Zoek op **de pagina & samenwerkingsrapporten** naar **Inzendingen** en klik vervolgens op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="b3318-421">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="b3318-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="b3318-422">Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Inzendingen op de pagina E-& samenwerkingsrapporten](../../media/submissions-report-widget.png)

<span data-ttu-id="b3318-424">In de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b3318-424">The chart shows the following information:</span></span>

- <span data-ttu-id="b3318-425">**In behandeling**</span><span class="sxs-lookup"><span data-stu-id="b3318-425">**Pending**</span></span>
- <span data-ttu-id="b3318-426">**Voltooid**</span><span class="sxs-lookup"><span data-stu-id="b3318-426">**Completed**</span></span>

<span data-ttu-id="b3318-427">Op de **pagina Inzendingen** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="b3318-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b3318-428">**Datum gerapporteerd:** **Begintijd** en **eindtijd**</span><span class="sxs-lookup"><span data-stu-id="b3318-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="b3318-429">**Inzendingstype:** **E-mail,** **URL** of **Bestand**</span><span class="sxs-lookup"><span data-stu-id="b3318-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="b3318-430">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="b3318-430">**Submission ID**</span></span>
- <span data-ttu-id="b3318-431">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="b3318-431">**Network Message ID**</span></span>
- <span data-ttu-id="b3318-432">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-432">**Sender**</span></span>
- <span data-ttu-id="b3318-433">**Naam**</span><span class="sxs-lookup"><span data-stu-id="b3318-433">**Name**</span></span>
- <span data-ttu-id="b3318-434">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="b3318-434">**Submitted by**</span></span>
- <span data-ttu-id="b3318-435">**Reden voor het indienen** van : **Geen ongewenste** e-mail, **Phish,** **Malware** of **Spam**</span><span class="sxs-lookup"><span data-stu-id="b3318-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="b3318-436">**Status opnieuw scannen:** **In behandeling** of **voltooid**</span><span class="sxs-lookup"><span data-stu-id="b3318-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="b3318-437">De detailtabel onder de grafiek bevat dezelfde  informatie en heeft  dezelfde opties voor groepen of kolommen aanpassen als op het tabblad Ingediend voor analyse op  **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="b3318-438">Zie Beheerdersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-admin-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="b3318-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Rapportpagina Inzendingen in de Microsoft 365 Defender portal](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="b3318-440">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="b3318-440">Threat protection status report</span></span>

<span data-ttu-id="b3318-441">Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Defender voor Office 365; De rapporten bevatten echter verschillende gegevens.</span><span class="sxs-lookup"><span data-stu-id="b3318-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="b3318-442">EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b3318-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b3318-443">Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische nul-uursre [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md) [Safe](safe-attachments.md)Bijlagen en functies voor imitatiebeveiliging [in anti-phishingbeleid.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b3318-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b3318-444">U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="b3318-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="b3318-445">**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="b3318-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b3318-446">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-447">Zoek op **de pagina & samenwerkingsrapporten** naar Status van **bedreigingsbeveiliging** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="b3318-448">Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:</span><span class="sxs-lookup"><span data-stu-id="b3318-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="b3318-449">Defender voor Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="b3318-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="b3318-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="b3318-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Statuswidget Bedreigingsbeveiliging op de pagina E-mail & samenwerkingsrapporten](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="b3318-452">Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b3318-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="b3318-453">Als u op  **Filter klikt** op de rapportpagina bedreigingsstatus, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen beperkt zijn tot 30 dagen).</span><span class="sxs-lookup"><span data-stu-id="b3318-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="b3318-454">Met de detailtabel kunt u 30 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="b3318-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="b3318-455">De beschikbare weergaven worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="b3318-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="b3318-456">Gegevens weergeven op overzicht</span><span class="sxs-lookup"><span data-stu-id="b3318-456">View data by Overview</span></span>

![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="b3318-458">In de **weergave Gegevens weergeven op** overzicht worden de volgende detectiegegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="b3318-459">**E-mailmalware**</span><span class="sxs-lookup"><span data-stu-id="b3318-459">**Email malware**</span></span>
- <span data-ttu-id="b3318-460">**E-mail phish**</span><span class="sxs-lookup"><span data-stu-id="b3318-460">**Email phish**</span></span>
- <span data-ttu-id="b3318-461">**Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="b3318-461">**Content malware**</span></span>

<span data-ttu-id="b3318-462">Er is geen detailtabel beschikbaar onder de grafiek.</span><span class="sxs-lookup"><span data-stu-id="b3318-462">No details table is available below the chart.</span></span>

<span data-ttu-id="b3318-463">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-464">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-465">**Detectie:** **E-mail malware,** **E-mail phish** of **Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="b3318-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="b3318-466">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-467">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-468">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-469">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-469">**Direction**</span></span>
- <span data-ttu-id="b3318-470">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-470">**Domain**</span></span>
- <span data-ttu-id="b3318-471">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-471">**Policy type**</span></span>

<span data-ttu-id="b3318-472">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="b3318-473">Gegevens weergeven op \> e-mail phish en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="b3318-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="b3318-475">In de **weergave Gegevens weergeven per \> e-mail phish** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="b3318-476">**URL-schadelijke reputatie**: Kwaadaardige URL-reputatie die is gegenereerd door Defender voor Office 365 <sup>\*</sup> detonaties in andere Microsoft 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="b3318-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="b3318-477">**Geavanceerd filter:** Phishing-signalen op basis van machine learning.</span><span class="sxs-lookup"><span data-stu-id="b3318-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="b3318-478">**Algemeen filter:** Phishing-signalen op basis van analistregels.</span><span class="sxs-lookup"><span data-stu-id="b3318-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="b3318-479">**Spoof intra-org:** Afzender probeert het domein van de geadresseerde te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="b3318-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="b3318-480">**Extern domein vervalsen:** afzender probeert een ander domein te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="b3318-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="b3318-481">**Spoof DMARC:** DMARC-verificatiefout op berichten.</span><span class="sxs-lookup"><span data-stu-id="b3318-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="b3318-482">**Imitatiemerk:** Imitatie van bekende merken op basis van afzenders.</span><span class="sxs-lookup"><span data-stu-id="b3318-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="b3318-483">**Detectie van gemengde analyse**</span><span class="sxs-lookup"><span data-stu-id="b3318-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="b3318-484">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-484">**File reputation**</span></span>
- <span data-ttu-id="b3318-485">**Vingerafdrukmatching**</span><span class="sxs-lookup"><span data-stu-id="b3318-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="b3318-486">**URL-detonatiereputatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-487">**URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-488">**Imitatiegebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-489">**Imitatiedomein:** imitatie van domeinen die de klant bezit <sup>\*</sup> of definieert.</span><span class="sxs-lookup"><span data-stu-id="b3318-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="b3318-490">**Postvakintelligentie** <sup>\*</sup> imiteren: Imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="b3318-491">**Bestandsdetonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-492">**Campagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="b3318-493">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-494">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-494">**Date**</span></span>
- <span data-ttu-id="b3318-495">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-495">**Subject**</span></span>
- <span data-ttu-id="b3318-496">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-496">**Sender**</span></span>
- <span data-ttu-id="b3318-497">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-497">**Recipients**</span></span>
- <span data-ttu-id="b3318-498">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-498">**Detected by**</span></span>
- <span data-ttu-id="b3318-499">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="b3318-499">**Delivery Status**</span></span>
- <span data-ttu-id="b3318-500">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="b3318-500">**Source of Compromise**</span></span>
- <span data-ttu-id="b3318-501">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-501">**Tags**</span></span>

<span data-ttu-id="b3318-502">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-503">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-504">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-504">**Detection**</span></span>
- <span data-ttu-id="b3318-505">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-506">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-506">**Direction**</span></span>
- <span data-ttu-id="b3318-507">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-508">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-509">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-509">**Domain**</span></span>
- <span data-ttu-id="b3318-510">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-510">**Policy type**</span></span>
- <span data-ttu-id="b3318-511">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="b3318-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b3318-512">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-512">**Recipients**</span></span>

<span data-ttu-id="b3318-513">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="b3318-514">Gegevens weergeven op \> e-mailmalware en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="b3318-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="b3318-516">In de **weergave Gegevens weergeven per e-mail \> malware** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="b3318-517">**Bestandsdetonatie** <sup>\*</sup> : Detectie door Safe bijlagen.</span><span class="sxs-lookup"><span data-stu-id="b3318-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="b3318-518">**Reputatie van bestandsdetonatie:** alle schadelijke bestandsreputatie die door Defender wordt gegenereerd <sup>\*</sup> Office 365 detonaties.</span><span class="sxs-lookup"><span data-stu-id="b3318-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="b3318-519">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-519">**File reputation**</span></span>
- <span data-ttu-id="b3318-520">**Anti-malware-engine:** <sup>\*</sup> Detectie van anti-malwareprogramma's.</span><span class="sxs-lookup"><span data-stu-id="b3318-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="b3318-521">**Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="b3318-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="b3318-522">**URL schadelijke reputatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="b3318-523">**URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-523">**URL detonation**</span></span>
- <span data-ttu-id="b3318-524">**URL-detonatiereputatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="b3318-525">**Campagne**</span><span class="sxs-lookup"><span data-stu-id="b3318-525">**Campaign**</span></span>

<span data-ttu-id="b3318-526">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-527">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-527">**Date**</span></span>
- <span data-ttu-id="b3318-528">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-528">**Subject**</span></span>
- <span data-ttu-id="b3318-529">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-529">**Sender**</span></span>
- <span data-ttu-id="b3318-530">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-530">**Recipients**</span></span>
- <span data-ttu-id="b3318-531">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-531">**Detected by**</span></span>
- <span data-ttu-id="b3318-532">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="b3318-532">**Delivery Status**</span></span>
- <span data-ttu-id="b3318-533">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="b3318-533">**Source of Compromise**</span></span>
- <span data-ttu-id="b3318-534">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-534">**Tags**</span></span>

<span data-ttu-id="b3318-535">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-536">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-537">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-537">**Detection**</span></span>
- <span data-ttu-id="b3318-538">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-539">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-539">**Direction**</span></span>
- <span data-ttu-id="b3318-540">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-541">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-542">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-542">**Domain**</span></span>
- <span data-ttu-id="b3318-543">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-543">**Policy type**</span></span>
- <span data-ttu-id="b3318-544">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="b3318-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b3318-545">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-545">**Recipients**</span></span>

<span data-ttu-id="b3318-546">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="b3318-547">Grafiekinsplitsing per type beleid en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per e-mail \> malware</span><span class="sxs-lookup"><span data-stu-id="b3318-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave beleidtype voor phishing-e-mail of malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="b3318-549">In de **uitsplitsing Grafiek op type beleid** en Gegevens weergeven per e-mail **\> Phish** of Weergave van gegevens per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="b3318-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="b3318-550">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="b3318-550">**Anti-malware**</span></span>
- <span data-ttu-id="b3318-551">**Safe Bijlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3318-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="b3318-552">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="b3318-552">**Anti-phish**</span></span>
- <span data-ttu-id="b3318-553">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="b3318-553">**Anti-spam**</span></span>
- <span data-ttu-id="b3318-554">**E-mailstroomregel** (ook wel transportregel genoemd)</span><span class="sxs-lookup"><span data-stu-id="b3318-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="b3318-555">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="b3318-555">**Others**</span></span>

<span data-ttu-id="b3318-556">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-557">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-557">**Date**</span></span>
- <span data-ttu-id="b3318-558">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-558">**Subject**</span></span>
- <span data-ttu-id="b3318-559">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-559">**Sender**</span></span>
- <span data-ttu-id="b3318-560">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-560">**Recipients**</span></span>
- <span data-ttu-id="b3318-561">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-561">**Detected by**</span></span>
- <span data-ttu-id="b3318-562">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="b3318-562">**Delivery Status**</span></span>
- <span data-ttu-id="b3318-563">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="b3318-563">**Source of Compromise**</span></span>
- <span data-ttu-id="b3318-564">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-564">**Tags**</span></span>

<span data-ttu-id="b3318-565">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-566">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-567">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-567">**Detection**</span></span>
- <span data-ttu-id="b3318-568">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-569">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-569">**Direction**</span></span>
- <span data-ttu-id="b3318-570">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-571">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-572">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-572">**Domain**</span></span>
- <span data-ttu-id="b3318-573">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-573">**Policy type**</span></span>
- <span data-ttu-id="b3318-574">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="b3318-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b3318-575">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-575">**Recipients**</span></span>

<span data-ttu-id="b3318-576">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="b3318-577">Grafiekinsplitsing op bezorgingsstatus en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per \> e-mail malware</span><span class="sxs-lookup"><span data-stu-id="b3318-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave bezorgingsstatus voor phishing-e-mail en malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="b3318-579">In de **uitsplitsing Grafiek per bezorgingsstatus** en **Gegevens weergeven per e-mail \> phish** of Gegevens weergeven per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="b3318-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="b3318-580">**Gehost postvak: Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="b3318-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="b3318-581">**Gehost postvak: Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="b3318-582">**Gehost postvak: aangepaste map**</span><span class="sxs-lookup"><span data-stu-id="b3318-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="b3318-583">**Gehost postvak: Verwijderde items**</span><span class="sxs-lookup"><span data-stu-id="b3318-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="b3318-584">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="b3318-584">**Forwarded**</span></span>
- <span data-ttu-id="b3318-585">**On-premises server: geleverd**</span><span class="sxs-lookup"><span data-stu-id="b3318-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="b3318-586">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="b3318-586">**Quarantine**</span></span>
- <span data-ttu-id="b3318-587">**Bezorging mislukt**</span><span class="sxs-lookup"><span data-stu-id="b3318-587">**Delivery failed**</span></span>
- <span data-ttu-id="b3318-588">**Laten vallen**</span><span class="sxs-lookup"><span data-stu-id="b3318-588">**Dropped**</span></span>

<span data-ttu-id="b3318-589">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-590">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-590">**Date**</span></span>
- <span data-ttu-id="b3318-591">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-591">**Subject**</span></span>
- <span data-ttu-id="b3318-592">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-592">**Sender**</span></span>
- <span data-ttu-id="b3318-593">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-593">**Recipients**</span></span>
- <span data-ttu-id="b3318-594">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-594">**Detected by**</span></span>
- <span data-ttu-id="b3318-595">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="b3318-595">**Delivery Status**</span></span>
- <span data-ttu-id="b3318-596">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="b3318-596">**Source of Compromise**</span></span>
- <span data-ttu-id="b3318-597">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-597">**Tags**</span></span>

<span data-ttu-id="b3318-598">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-599">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-600">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-600">**Detection**</span></span>
- <span data-ttu-id="b3318-601">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-602">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-602">**Direction**</span></span>
- <span data-ttu-id="b3318-603">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-604">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-605">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-605">**Domain**</span></span>
- <span data-ttu-id="b3318-606">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-606">**Policy type**</span></span>
- <span data-ttu-id="b3318-607">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="b3318-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b3318-608">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-608">**Recipients**</span></span>

<span data-ttu-id="b3318-609">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="b3318-610">Gegevens weergeven op \> inhoudsmalware</span><span class="sxs-lookup"><span data-stu-id="b3318-610">View data by Content \> Malware</span></span>

![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="b3318-612">In de **weergave Gegevens weergeven op \> inhoudsmalware** worden de volgende gegevens weergegeven in de grafiek voor Microsoft Defender voor Office 365 organisaties:</span><span class="sxs-lookup"><span data-stu-id="b3318-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="b3318-613">**Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="b3318-614">**Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b3318-615">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-616">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-617">**Locatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-617">**Location**</span></span>
- <span data-ttu-id="b3318-618">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-618">**Detected by**</span></span>
- <span data-ttu-id="b3318-619">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="b3318-619">**Malware name**</span></span>

<span data-ttu-id="b3318-620">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-621">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-622">**Detectie:** **Anti-malware-engine** of **Bestandsdetonatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="b3318-623">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="b3318-624">Gegevens weergeven op systeem overschrijven</span><span class="sxs-lookup"><span data-stu-id="b3318-624">View data by System override</span></span>

![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="b3318-626">In de **weergave Gegevens weergeven op systeem overschrijven** worden de volgende redengegevens overschrijven weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="b3318-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="b3318-627">**On-premises overslaan**</span><span class="sxs-lookup"><span data-stu-id="b3318-627">**On-premises skip**</span></span>
- <span data-ttu-id="b3318-628">**IP-toestaan**</span><span class="sxs-lookup"><span data-stu-id="b3318-628">**IP allow**</span></span>
- <span data-ttu-id="b3318-629">**Exchange regel voor e-mailtransport** (regel e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="b3318-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="b3318-630">**Organisatie toegestaan afzenders**</span><span class="sxs-lookup"><span data-stu-id="b3318-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="b3318-631">**Toegestane domeinen van de organisatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="b3318-632">**ZAP niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="b3318-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="b3318-633">**Map Ongewenste e-mail niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="b3318-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="b3318-634">**Gebruiker Safe afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-634">**User Safe Sender**</span></span>
- <span data-ttu-id="b3318-635">**User Safe Domain**</span><span class="sxs-lookup"><span data-stu-id="b3318-635">**User Safe Domain**</span></span>

<span data-ttu-id="b3318-636">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="b3318-637">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b3318-637">**Date**</span></span>
- <span data-ttu-id="b3318-638">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-638">**Subject**</span></span>
- <span data-ttu-id="b3318-639">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-639">**Sender**</span></span>
- <span data-ttu-id="b3318-640">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-640">**Recipients**</span></span>
- <span data-ttu-id="b3318-641">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-641">**Detected by**</span></span>
- <span data-ttu-id="b3318-642">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="b3318-642">**Delivery Status**</span></span>
- <span data-ttu-id="b3318-643">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="b3318-643">**Source of Compromise**</span></span>
- <span data-ttu-id="b3318-644">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-644">**Tags**</span></span>

<span data-ttu-id="b3318-645">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="b3318-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="b3318-646">**Datum (UTC)** **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="b3318-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="b3318-647">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="b3318-647">**Detection**</span></span>
- <span data-ttu-id="b3318-648">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="b3318-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="b3318-649">**Richting**</span><span class="sxs-lookup"><span data-stu-id="b3318-649">**Direction**</span></span>
- <span data-ttu-id="b3318-650">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="b3318-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b3318-651">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="b3318-652">**Domein**</span><span class="sxs-lookup"><span data-stu-id="b3318-652">**Domain**</span></span>
- <span data-ttu-id="b3318-653">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="b3318-653">**Policy type**</span></span>
- <span data-ttu-id="b3318-654">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="b3318-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="b3318-655">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="b3318-655">**Recipients**</span></span>

<span data-ttu-id="b3318-656">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b3318-657"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="b3318-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="b3318-658">Top malwarerapport</span><span class="sxs-lookup"><span data-stu-id="b3318-658">Top malware report</span></span>

<span data-ttu-id="b3318-659">Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b3318-660">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-661">Zoek op **de pagina & samenwerkingsrapporten** naar **Top malware** en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="b3318-662">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="b3318-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Top malware widget on the Email & collaboration reports page](../../media/top-malware-report-widget.png)

<span data-ttu-id="b3318-664">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="b3318-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="b3318-665">Op de **pagina Top malwarerapport** wordt een grotere versie van het cirkeldiagram weergegeven op de rapportpagina. In de detailtabel onder de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b3318-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="b3318-666">**Top malware**</span><span class="sxs-lookup"><span data-stu-id="b3318-666">**Top malware**</span></span>
- <span data-ttu-id="b3318-667">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="b3318-667">**Count**</span></span>

<span data-ttu-id="b3318-668">Als u op **Filter klikt,** kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="b3318-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="b3318-670">URL-bedreigingsbeveiligingsrapport</span><span class="sxs-lookup"><span data-stu-id="b3318-670">URL threat protection report</span></span>

<span data-ttu-id="b3318-671">Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3318-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b3318-672">Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="b3318-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="b3318-673">Rapport met gerapporteerde berichten van gebruiker</span><span class="sxs-lookup"><span data-stu-id="b3318-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3318-674">Als het rapport **Gerapporteerde** berichten van de gebruiker correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="b3318-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="b3318-675">Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3318-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="b3318-676">Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="b3318-677">Het **rapport Gerapporteerde** berichten van gebruiker bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoeging Rapportbericht of de invoeging [Phishing melden.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="b3318-678">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="b3318-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="b3318-679">Zoek op **de pagina E-& samenwerkingsrapporten** naar **Gerapporteerde** berichten van de gebruiker en klik vervolgens op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b3318-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="b3318-680">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="b3318-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="b3318-681">Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget met gerapporteerde berichten van gebruiker op de pagina E-mail & samenwerkingsrapporten](../../media/user-reported-messages-widget.png)

<span data-ttu-id="b3318-683">Op de **pagina Gerapporteerde** berichten van gebruiker kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b3318-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="b3318-684">**Datum gerapporteerd:** **Begintijd** en **eindtijd**</span><span class="sxs-lookup"><span data-stu-id="b3318-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="b3318-685">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-685">**Reported by**</span></span>
- <span data-ttu-id="b3318-686">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-686">**Email subject**</span></span>
- <span data-ttu-id="b3318-687">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="b3318-687">**Message reported ID**</span></span>
- <span data-ttu-id="b3318-688">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="b3318-688">**Network Message ID**</span></span>
- <span data-ttu-id="b3318-689">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-689">**Sender**</span></span>
- <span data-ttu-id="b3318-690">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="b3318-690">**Reported reason**</span></span>
  - <span data-ttu-id="b3318-691">**Geen ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="b3318-691">**Not junk**</span></span>
  - <span data-ttu-id="b3318-692">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="b3318-692">**Phish**</span></span>
  - <span data-ttu-id="b3318-693">**Spam**</span><span class="sxs-lookup"><span data-stu-id="b3318-693">**Spam**</span></span>
- <span data-ttu-id="b3318-694">**Phish-simulatie:** **Ja** of **Nee**</span><span class="sxs-lookup"><span data-stu-id="b3318-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="b3318-695">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="b3318-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="b3318-696">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="b3318-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="b3318-697">**Geen**</span><span class="sxs-lookup"><span data-stu-id="b3318-697">**None**</span></span>
- <span data-ttu-id="b3318-698">**Reden**</span><span class="sxs-lookup"><span data-stu-id="b3318-698">**Reason**</span></span>
- <span data-ttu-id="b3318-699">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-699">**Sender**</span></span>
- <span data-ttu-id="b3318-700">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-700">**Reported by**</span></span>
- <span data-ttu-id="b3318-701">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="b3318-701">**Rescan result**</span></span>
- <span data-ttu-id="b3318-702">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="b3318-702">**Phish simulation**</span></span>

![Rapport met gerapporteerde berichten van gebruiker](../../media/user-reported-messages-report.png)

<span data-ttu-id="b3318-704">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="b3318-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="b3318-705">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b3318-705">**Email subject**</span></span>
- <span data-ttu-id="b3318-706">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="b3318-706">**Reported by**</span></span>
- <span data-ttu-id="b3318-707">**Datum gerapporteerd**</span><span class="sxs-lookup"><span data-stu-id="b3318-707">**Date reported**</span></span>
- <span data-ttu-id="b3318-708">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b3318-708">**Sender**</span></span>
- <span data-ttu-id="b3318-709">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="b3318-709">**Reported reason**</span></span>
- <span data-ttu-id="b3318-710">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="b3318-710">**Rescan result**</span></span>
- <span data-ttu-id="b3318-711">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b3318-711">**Tags**</span></span>

<span data-ttu-id="b3318-712">Als u een bericht wilt verzenden naar Microsoft voor analyse, selecteert u de berichtinvoer in de tabel, klikt u op Verzenden bij **Microsoft** voor analyse en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="b3318-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="b3318-713">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="b3318-713">**Report clean**</span></span>
- <span data-ttu-id="b3318-714">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="b3318-714">**Report phishing**</span></span>
- <span data-ttu-id="b3318-715">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="b3318-715">**Report malware**</span></span>
- <span data-ttu-id="b3318-716">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="b3318-716">**Report spam**'</span></span>
- <span data-ttu-id="b3318-717">**Onderzoek starten** (Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="b3318-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b3318-718">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="b3318-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b3318-719">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="b3318-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="b3318-720">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="b3318-720">**Organization Management**</span></span>
- <span data-ttu-id="b3318-721">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="b3318-721">**Security Administrator**</span></span>
- <span data-ttu-id="b3318-722">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="b3318-722">**Security Reader**</span></span>
- <span data-ttu-id="b3318-723">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="b3318-723">**Global Reader**</span></span>

<span data-ttu-id="b3318-724">Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b3318-725">**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b3318-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b3318-726">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3318-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b3318-727">Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?</span><span class="sxs-lookup"><span data-stu-id="b3318-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b3318-728">Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="b3318-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b3318-729">Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="b3318-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3318-730">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b3318-730">Related topics</span></span>

[<span data-ttu-id="b3318-731">Bescherming tegen spam en anti-malware in EOP</span><span class="sxs-lookup"><span data-stu-id="b3318-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="b3318-732">Slimme rapporten en inzichten in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="b3318-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b3318-733">E-mailstroomrapporten weergeven in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="b3318-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="b3318-734">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3318-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
