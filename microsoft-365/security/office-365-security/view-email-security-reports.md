---
title: E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender-portal
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
description: Meer informatie over het zoeken en gebruiken van e-mailbeveiligingsrapporten voor uw organisatie. E-mailbeveiligingsrapporten zijn beschikbaar in de Microsoft 365 Defender-portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985203"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="ef7af-104">E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="ef7af-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ef7af-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ef7af-105">**Applies to**</span></span>
- [<span data-ttu-id="ef7af-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ef7af-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ef7af-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ef7af-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ef7af-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef7af-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ef7af-109">Er zijn diverse rapporten beschikbaar in de Microsoft 365 Defender-portal om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie <https://security.microsoft.com> beschermen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="ef7af-110">Als u de benodigde machtigingen [hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken  in de Microsoft 365 Defender-portal door naar Rapporten E-mail & samenwerking e-mail \>  \> **& samenwerkingsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-111">Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender-portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="ef7af-113">Voor sommige rapporten op de pagina **E-& samenwerkingsrapporten** is Microsoft Defender voor Office 365 vereist.</span><span class="sxs-lookup"><span data-stu-id="ef7af-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ef7af-114">Zie Defender voor [Office 365-rapporten weergeven in de Microsoft 365 Defender-portal](view-reports-for-mdo.md)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="ef7af-115">Rapporten die zijn gerelateerd aan e-mailstroom, zijn nu in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="ef7af-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ef7af-116">Zie E-mailstroomrapporten in het [nieuwe Exchange-beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)voor meer informatie over deze rapporten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="ef7af-117">Rapport over gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="ef7af-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="ef7af-118">Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="ef7af-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="ef7af-119">Het is niet beschikbaar in zelfstandige EOP-organisaties (Exchange Online Protection).</span><span class="sxs-lookup"><span data-stu-id="ef7af-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="ef7af-120">In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="ef7af-121">Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="ef7af-122">Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts.</span><span class="sxs-lookup"><span data-stu-id="ef7af-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="ef7af-123">Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Voor gecompromitteerde gebruikers op de pagina E-mail & samenwerkingsrapporten](../../media/compromised-users-report-widget.png)

<span data-ttu-id="ef7af-125">De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="ef7af-126">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-127">Klik **op Gecompromitteerde** gebruikers op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="ef7af-128">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="ef7af-129">Nadat u op **Details weergeven** hebt geklikt, kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ef7af-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ef7af-130">**Datum (UTC)**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="ef7af-131">**Activiteit**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-131">**Activity**:</span></span>
  - <span data-ttu-id="ef7af-132">**Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="ef7af-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="ef7af-133">**Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="ef7af-134">Wanneer u klaar bent met filteren, klikt u **op Toepassen of** **Annuleren.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="ef7af-136">In de tabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="ef7af-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="ef7af-137">**Aanmaaktijd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-137">**Creation time**</span></span>
- <span data-ttu-id="ef7af-138">**Gebruikers-id**</span><span class="sxs-lookup"><span data-stu-id="ef7af-138">**User ID**</span></span>
- <span data-ttu-id="ef7af-139">**Actie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="ef7af-140">Rapport met exchange-transportregel</span><span class="sxs-lookup"><span data-stu-id="ef7af-140">Exchange transport rule report</span></span>

<span data-ttu-id="ef7af-141">Het **rapport Exchange-transportregel** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="ef7af-142">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-143">Klik **op Exchange-transportregel** op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="ef7af-144">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange-transportregelwidget op de pagina E-mail & samenwerkingsrapporten](../../media/transport-rule-report-widget.png)

<span data-ttu-id="ef7af-146">Nadat u op **Details weergeven hebt geklikt,** zijn de volgende grafieken en gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="ef7af-147">**Gegevens weergeven op exchange-transportregels** \> **Grafiekuitsplitsing op richting:** in deze grafiek  ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="ef7af-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="ef7af-148">**Gegevens weergeven op exchange-transportregels** \> **Uitsplitsing van grafieken op ernst:** in deze grafiek ziet u het aantal berichten met hoge **ernst,** gemiddelde ernst en **lage ernst.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="ef7af-149">U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="ef7af-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="ef7af-150">Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="ef7af-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="ef7af-151">**Gegevens weergeven op DLP Exchange-transportregels** \> **Grafiekuitsplitsing op richting:** in deze grafiek  ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door regels voor preventie van gegevensverlies (DLP).</span><span class="sxs-lookup"><span data-stu-id="ef7af-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="ef7af-152">**Gegevens weergeven op DLP Exchange-transportregels** \> **Grafiekuitsplitsing op ernst:** in deze weergave ziet u het  aantal berichten met hoge **ernst,** gemiddelde ernst en lage ernst die zijn beïnvloed door DLP-regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="ef7af-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="ef7af-153">Voor **selecties van gegevens per Exchange-transportregels** worden de volgende gegevens weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="ef7af-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-154">**Date**</span></span>
- <span data-ttu-id="ef7af-155">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="ef7af-155">**Transport rule**</span></span>
- <span data-ttu-id="ef7af-156">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-156">**Subject**</span></span>
- <span data-ttu-id="ef7af-157">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-157">**Sender address**</span></span>
- <span data-ttu-id="ef7af-158">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ef7af-158">**Recipient address**</span></span>
- <span data-ttu-id="ef7af-159">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="ef7af-159">**Severity**</span></span>
- <span data-ttu-id="ef7af-160">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-160">**Direction**</span></span>

<span data-ttu-id="ef7af-161">Voor **selecties van gegevens per DLP Exchange-transportregels** worden de volgende gegevens weergegeven in de detailtabel onder de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="ef7af-162">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-162">**Date**</span></span>
- <span data-ttu-id="ef7af-163">**DLP-beleid**</span><span class="sxs-lookup"><span data-stu-id="ef7af-163">**DLP policy**</span></span>
- <span data-ttu-id="ef7af-164">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="ef7af-164">**Transport rule**</span></span>
- <span data-ttu-id="ef7af-165">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-165">**Subject**</span></span>
- <span data-ttu-id="ef7af-166">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-166">**Sender address**</span></span>
- <span data-ttu-id="ef7af-167">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ef7af-167">**Recipient address**</span></span>
- <span data-ttu-id="ef7af-168">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="ef7af-168">**Severity**</span></span>
- <span data-ttu-id="ef7af-169">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-169">**Direction**</span></span>

<span data-ttu-id="ef7af-170">U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ef7af-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ef7af-171">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-172">**Richting:** **Uitgaande en Inkomende** </span><span class="sxs-lookup"><span data-stu-id="ef7af-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="ef7af-173">**Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**</span><span class="sxs-lookup"><span data-stu-id="ef7af-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Rapportweergave in het rapport Exchange-transportregel](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="ef7af-175">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="ef7af-175">Mailflow status report</span></span>

<span data-ttu-id="ef7af-176">Het **mailflowstatusrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, spamdetecties, malware, e-mail die als 'goed' is geïdentificeerd en informatie over e-mail die is toegestaan of geblokkeerd op de rand.</span><span class="sxs-lookup"><span data-stu-id="ef7af-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="ef7af-177">Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat e-mail wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="ef7af-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="ef7af-178">Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="ef7af-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="ef7af-179">Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-180">Klik **in het overzicht mailflowstatus** op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="ef7af-181">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Overzichtswidget Mailflow-status op de pagina E-mail & samenwerkingsrapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="ef7af-183">Typweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="ef7af-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="ef7af-184">Wanneer u het rapport opent, is **het tabblad Type** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="ef7af-185">Standaard bevat deze weergave een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="ef7af-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ef7af-186">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="ef7af-187">**E-mailrichting**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-187">**Mail direction**:</span></span>
  - <span data-ttu-id="ef7af-188">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="ef7af-188">**Inbound**</span></span>
  - <span data-ttu-id="ef7af-189">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="ef7af-189">**Outbound**</span></span>
  - <span data-ttu-id="ef7af-190">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="ef7af-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="ef7af-191">afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)</span><span class="sxs-lookup"><span data-stu-id="ef7af-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="ef7af-192">**Typ**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-192">**Type**:</span></span>
  - <span data-ttu-id="ef7af-193">**Goede e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-193">**Good mail**</span></span>
  - <span data-ttu-id="ef7af-194">**Malware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-194">**Malware**</span></span>
  - <span data-ttu-id="ef7af-195">**Spam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-195">**Spam**</span></span>
  - <span data-ttu-id="ef7af-196">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="ef7af-196">**Edge protection**</span></span>
  - <span data-ttu-id="ef7af-197">**Regelberichten**</span><span class="sxs-lookup"><span data-stu-id="ef7af-197">**Rule messages**</span></span>
  - <span data-ttu-id="ef7af-198">**Phishing-e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-198">**Phishing email**</span></span>
- <span data-ttu-id="ef7af-199">**Domein:** **Alles**</span><span class="sxs-lookup"><span data-stu-id="ef7af-199">**Domain**: **All**</span></span>

<span data-ttu-id="ef7af-200">De grafiek wordt ingedeeld op basis van **de waarden Type.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="ef7af-201">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="ef7af-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="ef7af-202">De gegevenstabel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="ef7af-202">The data table contains the following information:</span></span>

- <span data-ttu-id="ef7af-203">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-203">**Direction**</span></span>
- <span data-ttu-id="ef7af-204">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef7af-204">**Type**</span></span>
- <span data-ttu-id="ef7af-205">**24 uur**</span><span class="sxs-lookup"><span data-stu-id="ef7af-205">**24 hours**</span></span>
- <span data-ttu-id="ef7af-206">**3 dagen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-206">**3 days**</span></span>
- <span data-ttu-id="ef7af-207">**7 dagen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-207">**7 days**</span></span>
- <span data-ttu-id="ef7af-208">**15 dagen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-208">**15 days**</span></span>
- <span data-ttu-id="ef7af-209">**30 dagen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-209">**30 days**</span></span>

<span data-ttu-id="ef7af-210">Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="ef7af-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="ef7af-211">**Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="ef7af-212">**Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="ef7af-213">**Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="ef7af-214">**Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="ef7af-215">Exporteren vanuit de weergave Type</span><span class="sxs-lookup"><span data-stu-id="ef7af-215">Export from Type view</span></span>

<span data-ttu-id="ef7af-216">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="ef7af-217">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="ef7af-218">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ef7af-219">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Weergave typen in het rapport Mailflow-status](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="ef7af-221">Richtingsweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="ef7af-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="ef7af-222">Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="ef7af-223">De grafiek is ingedeeld op **richtingswaarden.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="ef7af-224">U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="ef7af-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="ef7af-225">Dezelfde filters uit de **weergave Type** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="ef7af-226">De gegevenstabel bevat dezelfde informatie uit de **weergave Type.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="ef7af-227">De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.</span><span class="sxs-lookup"><span data-stu-id="ef7af-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="ef7af-228">Exporteren vanuit de richtingsweergave</span><span class="sxs-lookup"><span data-stu-id="ef7af-228">Export from Direction view</span></span>

<span data-ttu-id="ef7af-229">Voor de detailweergave kunt u slechts één dag gegevens exporteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="ef7af-230">Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="ef7af-231">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ef7af-232">Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Richtingsweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="ef7af-234">Trechterweergave voor het rapport Mailflow-status</span><span class="sxs-lookup"><span data-stu-id="ef7af-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="ef7af-235">In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="ef7af-236">Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.</span><span class="sxs-lookup"><span data-stu-id="ef7af-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="ef7af-237">Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="ef7af-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ef7af-238">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="ef7af-239">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-239">**Direction**:</span></span>

  - <span data-ttu-id="ef7af-240">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="ef7af-240">**Inbound**</span></span>
  - <span data-ttu-id="ef7af-241">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="ef7af-241">**Outbound**</span></span>
  - <span data-ttu-id="ef7af-242">**Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).</span><span class="sxs-lookup"><span data-stu-id="ef7af-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="ef7af-243">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="ef7af-244">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="ef7af-245">In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:</span><span class="sxs-lookup"><span data-stu-id="ef7af-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="ef7af-246">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-246">**Total email**</span></span>
- <span data-ttu-id="ef7af-247">**E-mail na randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="ef7af-247">**Email after edge protection**</span></span>
- <span data-ttu-id="ef7af-248">**Regel E-mail na transport** (regel voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="ef7af-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="ef7af-249">**E-mail na anti-malware, bestandsreputatie, bestandstypeblok**</span><span class="sxs-lookup"><span data-stu-id="ef7af-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="ef7af-250">**E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="ef7af-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="ef7af-251">**E-mail na antispam, bulkmailfilters**</span><span class="sxs-lookup"><span data-stu-id="ef7af-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="ef7af-252">**E-mail na gebruikers- en domein-imitatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-253">**E-mail na bestand en URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-254">**E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**</span><span class="sxs-lookup"><span data-stu-id="ef7af-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="ef7af-255"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="ef7af-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="ef7af-256">Als u het e-mailbericht wilt weergeven dat is gefilterd op EOP of Defender Office 365 afzonderlijk, klikt u op de waarde in de grafieklegenda.</span><span class="sxs-lookup"><span data-stu-id="ef7af-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="ef7af-257">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="ef7af-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="ef7af-258">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-258">**Date**</span></span>
- <span data-ttu-id="ef7af-259">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-259">**Total email**</span></span>
- <span data-ttu-id="ef7af-260">**Randbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="ef7af-260">**Edge protection**</span></span>
- <span data-ttu-id="ef7af-261">**Anti-malware, bestandsreputatie, bestandstypeblok:**</span><span class="sxs-lookup"><span data-stu-id="ef7af-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="ef7af-262">**Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="ef7af-263">**Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="ef7af-264">**Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**</span><span class="sxs-lookup"><span data-stu-id="ef7af-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="ef7af-265">**URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="ef7af-266">**Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.</span><span class="sxs-lookup"><span data-stu-id="ef7af-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="ef7af-267">**Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.</span><span class="sxs-lookup"><span data-stu-id="ef7af-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="ef7af-268">**Antispam, bulkmailfilters:**</span><span class="sxs-lookup"><span data-stu-id="ef7af-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="ef7af-269">**Bulkmailfilters:** Berichten gefilterd op basis van de drempel voor bulksgewijs klagen (BCL) in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="ef7af-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="ef7af-270">**Gebruikers- en domein-imitatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="ef7af-271">**Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="ef7af-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="ef7af-272">**Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="ef7af-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="ef7af-273">**Bestands- en URL-detonatie (Defender voor Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="ef7af-274">**Bestandsdetonatie:** Berichten gefilterd op een Safe bijlagenbeleid.</span><span class="sxs-lookup"><span data-stu-id="ef7af-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="ef7af-275">**URL-detonatie:** bericht gefilterd door een Safe koppelingenbeleid.</span><span class="sxs-lookup"><span data-stu-id="ef7af-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="ef7af-276">**Bescherming na bezorging en ZAP (ATP) of ZAP (EOP)**: Automatische purge (ZAP) van nul uur voor malware, spam en phishing.</span><span class="sxs-lookup"><span data-stu-id="ef7af-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="ef7af-277">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="ef7af-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="ef7af-278">Exporteren vanuit de trechterweergave</span><span class="sxs-lookup"><span data-stu-id="ef7af-278">Export from Funnel view</span></span>

<span data-ttu-id="ef7af-279">Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: </span><span class="sxs-lookup"><span data-stu-id="ef7af-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="ef7af-280">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="ef7af-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="ef7af-281">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="ef7af-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="ef7af-282">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="ef7af-283">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="ef7af-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="ef7af-284">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ef7af-285">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Trechterweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="ef7af-287">Technische weergave voor het mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="ef7af-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="ef7af-288">De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="ef7af-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="ef7af-289">In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="ef7af-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="ef7af-290">Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="ef7af-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="ef7af-291">**Datum:** De laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="ef7af-292">**Richting**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-292">**Direction**:</span></span>

  - <span data-ttu-id="ef7af-293">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="ef7af-293">**Inbound**</span></span>
  - <span data-ttu-id="ef7af-294">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="ef7af-294">**Outbound**</span></span>
  - <span data-ttu-id="ef7af-295">**Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen</span><span class="sxs-lookup"><span data-stu-id="ef7af-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="ef7af-296">afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)</span><span class="sxs-lookup"><span data-stu-id="ef7af-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="ef7af-297">De statistische weergave en gegevenstabelweergave kunnen 90 dagen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="ef7af-298">Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="ef7af-299">In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="ef7af-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="ef7af-300">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-300">**Total email**</span></span>
- <span data-ttu-id="ef7af-301">**Rand toestaan** en **Edge gefilterd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="ef7af-302">**Transportregel toestaan** en **Transportregel gefilterd** (regels voor e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="ef7af-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="ef7af-303">**Geen malware,** **Safe detectie van** bijlagen en detectie van <sup>\*</sup> **anti-malware-engine**</span><span class="sxs-lookup"><span data-stu-id="ef7af-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="ef7af-304">**Geen phish,** **DMARC-fout,** **imitatiedetectie,** <sup>\*</sup> **spoofdetectie** en **Phish-detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="ef7af-305">**Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-306">**Geen spam en**  **spam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="ef7af-307">**Niet-schadelijke e-mail,** **Safe koppelingendetectie** <sup>\*</sup> en **ZAP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="ef7af-308"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ef7af-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="ef7af-309">Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.</span><span class="sxs-lookup"><span data-stu-id="ef7af-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="ef7af-310">De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:</span><span class="sxs-lookup"><span data-stu-id="ef7af-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="ef7af-311">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-311">**Date**</span></span>
- <span data-ttu-id="ef7af-312">**Totaal aantal e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-312">**Total email**</span></span>
- <span data-ttu-id="ef7af-313">**Gefilterde rand**</span><span class="sxs-lookup"><span data-stu-id="ef7af-313">**Edge filtered**</span></span>
- <span data-ttu-id="ef7af-314">**Regelberichten:** Berichten die zijn gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="ef7af-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="ef7af-315">**Anti-malware engine**, **Safe Bijlagen:** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="ef7af-316">**DMARC, imitatie** <sup>\*</sup> , **spoof**, **phish gefilterd**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="ef7af-317">**DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="ef7af-318">**DETECTIE VAN URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-319">**Gefilterde antispam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="ef7af-320">**ZAP verwijderd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-320">**ZAP removed**</span></span>
- <span data-ttu-id="ef7af-321">**Detectie door Safe koppelingen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="ef7af-322"><sup>\*</sup>Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ef7af-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="ef7af-323">Als u een rij in de gegevenstabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.</span><span class="sxs-lookup"><span data-stu-id="ef7af-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="ef7af-324">Exporteren vanuit de techweergave</span><span class="sxs-lookup"><span data-stu-id="ef7af-324">Export from Tech view</span></span>

<span data-ttu-id="ef7af-325">Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:</span><span class="sxs-lookup"><span data-stu-id="ef7af-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="ef7af-326">**Overzicht (met gegevens van de afgelopen 90 dagen)**</span><span class="sxs-lookup"><span data-stu-id="ef7af-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="ef7af-327">**Details (met gegevens van de afgelopen 30 dagen ten hoogst)**</span><span class="sxs-lookup"><span data-stu-id="ef7af-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="ef7af-328">Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="ef7af-329">Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="ef7af-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="ef7af-330">Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="ef7af-331">Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ef7af-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Technische weergave in het rapport Mailflow-status](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="ef7af-333">Rapport malwaredetecties</span><span class="sxs-lookup"><span data-stu-id="ef7af-333">Malware detections report</span></span>

<span data-ttu-id="ef7af-334">Het **rapport Malwaredetecties bevat** informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP).</span><span class="sxs-lookup"><span data-stu-id="ef7af-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="ef7af-335">Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.</span><span class="sxs-lookup"><span data-stu-id="ef7af-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="ef7af-336">Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.</span><span class="sxs-lookup"><span data-stu-id="ef7af-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="ef7af-337">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-338">Klik **op Malware gedetecteerd in e-mail** op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="ef7af-339">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Malwaredetecties in e-mailwidget op de pagina E-mail & samenwerkingsrapporten](../../media/malware-detections-widget.png)

<span data-ttu-id="ef7af-341">Nadat u op **Details weergeven hebt** geklikt, kunt u zowel de grafiek als de detailtabel filteren door te klikken op **Filteren** en te selecteren:</span><span class="sxs-lookup"><span data-stu-id="ef7af-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="ef7af-342">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-343">**Richting:** **Binnenkomende** en **uitgaande**</span><span class="sxs-lookup"><span data-stu-id="ef7af-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

<span data-ttu-id="ef7af-345">In de detailtabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="ef7af-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="ef7af-346">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-346">**Date**</span></span>
- <span data-ttu-id="ef7af-347">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-347">**Sender address**</span></span>
- <span data-ttu-id="ef7af-348">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ef7af-348">**Recipient address**</span></span>
- <span data-ttu-id="ef7af-349">**Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="ef7af-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="ef7af-350">Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).</span><span class="sxs-lookup"><span data-stu-id="ef7af-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="ef7af-351">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-351">**Subject**</span></span>
- <span data-ttu-id="ef7af-352">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-352">**Filename**</span></span>
- <span data-ttu-id="ef7af-353">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="ef7af-354">E-maillatentierapport</span><span class="sxs-lookup"><span data-stu-id="ef7af-354">Mail latency report</span></span>

<span data-ttu-id="ef7af-355">Het **rapport E-maillatentie** in Defender voor Office 365 bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="ef7af-356">Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="ef7af-357">Rapport over spamdetectie</span><span class="sxs-lookup"><span data-stu-id="ef7af-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="ef7af-358">Het **rapport Spamdetecties** gaat op 30 juni 2021 weg.</span><span class="sxs-lookup"><span data-stu-id="ef7af-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="ef7af-359">Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="ef7af-360">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="ef7af-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="ef7af-361">Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="ef7af-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="ef7af-362">In de oudere versie van het rapport ziet u alleen **Goede e-mail** en **Gevangen als spam.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="ef7af-363">Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing.</span><span class="sxs-lookup"><span data-stu-id="ef7af-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="ef7af-364">Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="ef7af-365">Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.</span><span class="sxs-lookup"><span data-stu-id="ef7af-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="ef7af-366"><sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ef7af-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="ef7af-367">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-368">Klik **bij Spoofdetecties** op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="ef7af-369">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Spoofdetecties op de pagina E-mail & samenwerkingsrapporten](../../media/spoof-detections-widget.png)

<span data-ttu-id="ef7af-371">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.</span><span class="sxs-lookup"><span data-stu-id="ef7af-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="ef7af-372">Nadat u op **Details weergeven hebt** geklikt, kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="ef7af-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="ef7af-373">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-374">**Resultaat**:</span><span class="sxs-lookup"><span data-stu-id="ef7af-374">**Result**:</span></span>
  - <span data-ttu-id="ef7af-375">**Pass**</span><span class="sxs-lookup"><span data-stu-id="ef7af-375">**Pass**</span></span>
  - <span data-ttu-id="ef7af-376">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="ef7af-376">**Fail**</span></span>
  - <span data-ttu-id="ef7af-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="ef7af-377">**SoftPass**</span></span>
  - <span data-ttu-id="ef7af-378">**Geen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-378">**None**</span></span>
  - <span data-ttu-id="ef7af-379">**Overige**</span><span class="sxs-lookup"><span data-stu-id="ef7af-379">**Other**</span></span>
- <span data-ttu-id="ef7af-380">**Spooftype:** **Intern** en **Extern**</span><span class="sxs-lookup"><span data-stu-id="ef7af-380">**Spoof type**: **Internal** and **External**</span></span>

![Pagina spoof-e-mailrapport in de Microsoft 365 Defender portal](../../media/spoof-detections-report-page.png)

<span data-ttu-id="ef7af-382">In de tabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="ef7af-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="ef7af-383">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-383">**Date**</span></span>
- <span data-ttu-id="ef7af-384">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="ef7af-384">**Spoofed user**</span></span>
- <span data-ttu-id="ef7af-385">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="ef7af-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="ef7af-386">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-386">**Spoof type**</span></span>
- <span data-ttu-id="ef7af-387">**Result**</span><span class="sxs-lookup"><span data-stu-id="ef7af-387">**Result**</span></span>
- <span data-ttu-id="ef7af-388">**Resultaatcode**</span><span class="sxs-lookup"><span data-stu-id="ef7af-388">**Result code**</span></span>
- <span data-ttu-id="ef7af-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="ef7af-389">**SPF**</span></span>
- <span data-ttu-id="ef7af-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="ef7af-390">**DKIM**</span></span>
- <span data-ttu-id="ef7af-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="ef7af-391">**DMARC**</span></span>
- <span data-ttu-id="ef7af-392">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="ef7af-392">**Message count**</span></span>

<span data-ttu-id="ef7af-393">Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ef7af-394">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="ef7af-394">Threat protection status report</span></span>

<span data-ttu-id="ef7af-395">Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Defender voor Office 365; De rapporten bevatten echter verschillende gegevens.</span><span class="sxs-lookup"><span data-stu-id="ef7af-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="ef7af-396">EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ef7af-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ef7af-397">Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische nul-uursre [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md) [Safe](safe-attachments.md)Bijlagen en functies voor imitatiebeveiliging [in anti-phishingbeleid.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="ef7af-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="ef7af-398">U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="ef7af-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="ef7af-399">**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="ef7af-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="ef7af-400">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-401">Klik **op Bedreigingsbeveiliging** op **Details weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="ef7af-402">Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:</span><span class="sxs-lookup"><span data-stu-id="ef7af-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="ef7af-403">Defender voor Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="ef7af-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="ef7af-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="ef7af-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Statuswidget Bedreigingsbeveiliging op de pagina E-mail & samenwerkingsrapporten](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="ef7af-406">Nadat u op Details weergeven **hebt** geklikt, worden in de grafiek standaard gegevens van de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ef7af-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="ef7af-407">Als u op **Filter** klikt, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen beperkt zijn tot 30 dagen).</span><span class="sxs-lookup"><span data-stu-id="ef7af-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="ef7af-408">Met de detailtabel kunt u 30 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="ef7af-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="ef7af-409">De beschikbare weergaven worden in de volgende secties beschreven.</span><span class="sxs-lookup"><span data-stu-id="ef7af-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="ef7af-410">Gegevens weergeven op overzicht</span><span class="sxs-lookup"><span data-stu-id="ef7af-410">View data by Overview</span></span>

![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="ef7af-412">In de **weergave Gegevens weergeven op** overzicht worden de volgende detectiegegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="ef7af-413">**E-mailmalware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-413">**Email malware**</span></span>
- <span data-ttu-id="ef7af-414">**E-mail phish**</span><span class="sxs-lookup"><span data-stu-id="ef7af-414">**Email phish**</span></span>
- <span data-ttu-id="ef7af-415">**Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-415">**Content malware**</span></span>

<span data-ttu-id="ef7af-416">Er is geen detailtabel beschikbaar onder de grafiek.</span><span class="sxs-lookup"><span data-stu-id="ef7af-416">No details table is available below the chart.</span></span>

<span data-ttu-id="ef7af-417">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-418">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-419">**Detectie:** **E-mail malware,** **E-mail phish** of **Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="ef7af-420">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-421">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-422">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-423">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-423">**Direction**</span></span>
- <span data-ttu-id="ef7af-424">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-424">**Domain**</span></span>
- <span data-ttu-id="ef7af-425">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-425">**Policy type**</span></span>

<span data-ttu-id="ef7af-426">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="ef7af-427">Gegevens weergeven op \> e-mail phish en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="ef7af-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="ef7af-429">In de **weergave Gegevens weergeven per \> e-mail phish** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="ef7af-430">**URL-schadelijke reputatie**: Kwaadaardige URL-reputatie die is gegenereerd door Defender voor Office 365 <sup>\*</sup> detonaties in andere Microsoft 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="ef7af-431">**Geavanceerd filter:** Phishing-signalen op basis van machine learning.</span><span class="sxs-lookup"><span data-stu-id="ef7af-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="ef7af-432">**Algemeen filter:** Phishing-signalen op basis van analistregels.</span><span class="sxs-lookup"><span data-stu-id="ef7af-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="ef7af-433">**Spoof intra-org:** Afzender probeert het domein van de geadresseerde te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="ef7af-434">**Extern domein vervalsen:** afzender probeert een ander domein te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="ef7af-435">**Spoof DMARC:** DMARC-verificatiefout op berichten.</span><span class="sxs-lookup"><span data-stu-id="ef7af-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="ef7af-436">**Imitatiemerk:** Imitatie van bekende merken op basis van afzenders.</span><span class="sxs-lookup"><span data-stu-id="ef7af-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="ef7af-437">**Detectie van gemengde analyse**</span><span class="sxs-lookup"><span data-stu-id="ef7af-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="ef7af-438">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-438">**File reputation**</span></span>
- <span data-ttu-id="ef7af-439">**Vingerafdrukmatching**</span><span class="sxs-lookup"><span data-stu-id="ef7af-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="ef7af-440">**URL-detonatiereputatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-441">**URL-detonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-442">**Imitatiegebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-443">**Imitatiedomein:** imitatie van domeinen die de klant bezit <sup>\*</sup> of definieert.</span><span class="sxs-lookup"><span data-stu-id="ef7af-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="ef7af-444">**Postvakintelligentie** <sup>\*</sup> imiteren: Imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="ef7af-445">**Bestandsdetonatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-446">**Campagne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="ef7af-447">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-448">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-448">**Date**</span></span>
- <span data-ttu-id="ef7af-449">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-449">**Subject**</span></span>
- <span data-ttu-id="ef7af-450">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-450">**Sender**</span></span>
- <span data-ttu-id="ef7af-451">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-451">**Recipients**</span></span>
- <span data-ttu-id="ef7af-452">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-452">**Detected by**</span></span>
- <span data-ttu-id="ef7af-453">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="ef7af-453">**Delivery Status**</span></span>
- <span data-ttu-id="ef7af-454">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="ef7af-454">**Source of Compromise**</span></span>
- <span data-ttu-id="ef7af-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-455">**Tags**</span></span>

<span data-ttu-id="ef7af-456">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-457">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-458">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-458">**Detection**</span></span>
- <span data-ttu-id="ef7af-459">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-460">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-460">**Direction**</span></span>
- <span data-ttu-id="ef7af-461">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-462">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-463">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-463">**Domain**</span></span>
- <span data-ttu-id="ef7af-464">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-464">**Policy type**</span></span>
- <span data-ttu-id="ef7af-465">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="ef7af-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="ef7af-466">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-466">**Recipients**</span></span>

<span data-ttu-id="ef7af-467">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="ef7af-468">Gegevens weergeven op \> e-mailmalware en grafiek met detectietechnologie</span><span class="sxs-lookup"><span data-stu-id="ef7af-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="ef7af-470">In de **weergave Gegevens weergeven per e-mail \> malware** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="ef7af-471">**Bestandsdetonatie** <sup>\*</sup> : Detectie door Safe bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ef7af-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="ef7af-472">**Reputatie van bestandsdetonatie:** alle schadelijke bestandsreputatie die door Defender wordt gegenereerd <sup>\*</sup> Office 365 detonaties.</span><span class="sxs-lookup"><span data-stu-id="ef7af-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="ef7af-473">**Bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-473">**File reputation**</span></span>
- <span data-ttu-id="ef7af-474">**Anti-malware-engine:** <sup>\*</sup> Detectie van anti-malwareprogramma's.</span><span class="sxs-lookup"><span data-stu-id="ef7af-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="ef7af-475">**Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="ef7af-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="ef7af-476">**URL schadelijke reputatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="ef7af-477">**URL-detonatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-477">**URL detonation**</span></span>
- <span data-ttu-id="ef7af-478">**URL-detonatiereputatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="ef7af-479">**Campagne**</span><span class="sxs-lookup"><span data-stu-id="ef7af-479">**Campaign**</span></span>

<span data-ttu-id="ef7af-480">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-481">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-481">**Date**</span></span>
- <span data-ttu-id="ef7af-482">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-482">**Subject**</span></span>
- <span data-ttu-id="ef7af-483">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-483">**Sender**</span></span>
- <span data-ttu-id="ef7af-484">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-484">**Recipients**</span></span>
- <span data-ttu-id="ef7af-485">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-485">**Detected by**</span></span>
- <span data-ttu-id="ef7af-486">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="ef7af-486">**Delivery Status**</span></span>
- <span data-ttu-id="ef7af-487">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="ef7af-487">**Source of Compromise**</span></span>
- <span data-ttu-id="ef7af-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-488">**Tags**</span></span>

<span data-ttu-id="ef7af-489">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-490">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-491">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-491">**Detection**</span></span>
- <span data-ttu-id="ef7af-492">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-493">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-493">**Direction**</span></span>
- <span data-ttu-id="ef7af-494">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-495">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-496">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-496">**Domain**</span></span>
- <span data-ttu-id="ef7af-497">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-497">**Policy type**</span></span>
- <span data-ttu-id="ef7af-498">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="ef7af-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="ef7af-499">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-499">**Recipients**</span></span>

<span data-ttu-id="ef7af-500">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="ef7af-501">Grafiekinsplitsing per type beleid en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per e-mail \> malware</span><span class="sxs-lookup"><span data-stu-id="ef7af-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave beleidtype voor phishing-e-mail of malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="ef7af-503">In de **uitsplitsing Grafiek op type beleid** en Gegevens weergeven per e-mail **\> Phish** of Weergave van gegevens per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="ef7af-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="ef7af-504">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-504">**Anti-malware**</span></span>
- <span data-ttu-id="ef7af-505">**Safe Bijlagen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ef7af-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="ef7af-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="ef7af-506">**Anti-phish**</span></span>
- <span data-ttu-id="ef7af-507">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-507">**Anti-spam**</span></span>
- <span data-ttu-id="ef7af-508">**E-mailstroomregel** (ook wel transportregel genoemd)</span><span class="sxs-lookup"><span data-stu-id="ef7af-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="ef7af-509">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-509">**Others**</span></span>

<span data-ttu-id="ef7af-510">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-511">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-511">**Date**</span></span>
- <span data-ttu-id="ef7af-512">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-512">**Subject**</span></span>
- <span data-ttu-id="ef7af-513">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-513">**Sender**</span></span>
- <span data-ttu-id="ef7af-514">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-514">**Recipients**</span></span>
- <span data-ttu-id="ef7af-515">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-515">**Detected by**</span></span>
- <span data-ttu-id="ef7af-516">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="ef7af-516">**Delivery Status**</span></span>
- <span data-ttu-id="ef7af-517">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="ef7af-517">**Source of Compromise**</span></span>
- <span data-ttu-id="ef7af-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-518">**Tags**</span></span>

<span data-ttu-id="ef7af-519">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-520">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-521">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-521">**Detection**</span></span>
- <span data-ttu-id="ef7af-522">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-523">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-523">**Direction**</span></span>
- <span data-ttu-id="ef7af-524">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-525">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-526">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-526">**Domain**</span></span>
- <span data-ttu-id="ef7af-527">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-527">**Policy type**</span></span>
- <span data-ttu-id="ef7af-528">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="ef7af-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="ef7af-529">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-529">**Recipients**</span></span>

<span data-ttu-id="ef7af-530">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="ef7af-531">Grafiekinsplitsing op bezorgingsstatus en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per \> e-mail malware</span><span class="sxs-lookup"><span data-stu-id="ef7af-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Weergave bezorgingsstatus voor phishing-e-mail en malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="ef7af-533">In de **uitsplitsing Grafiek per bezorgingsstatus** en **Gegevens weergeven per e-mail \> phish** of Gegevens weergeven per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:</span><span class="sxs-lookup"><span data-stu-id="ef7af-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="ef7af-534">**Gehost postvak: Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="ef7af-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="ef7af-535">**Gehost postvak: Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="ef7af-536">**Gehost postvak: aangepaste map**</span><span class="sxs-lookup"><span data-stu-id="ef7af-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="ef7af-537">**Gehost postvak: Verwijderde items**</span><span class="sxs-lookup"><span data-stu-id="ef7af-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="ef7af-538">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-538">**Forwarded**</span></span>
- <span data-ttu-id="ef7af-539">**On-premises server: geleverd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="ef7af-540">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="ef7af-540">**Quarantine**</span></span>
- <span data-ttu-id="ef7af-541">**Bezorging mislukt**</span><span class="sxs-lookup"><span data-stu-id="ef7af-541">**Delivery failed**</span></span>
- <span data-ttu-id="ef7af-542">**Laten vallen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-542">**Dropped**</span></span>

<span data-ttu-id="ef7af-543">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-544">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-544">**Date**</span></span>
- <span data-ttu-id="ef7af-545">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-545">**Subject**</span></span>
- <span data-ttu-id="ef7af-546">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-546">**Sender**</span></span>
- <span data-ttu-id="ef7af-547">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-547">**Recipients**</span></span>
- <span data-ttu-id="ef7af-548">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-548">**Detected by**</span></span>
- <span data-ttu-id="ef7af-549">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="ef7af-549">**Delivery Status**</span></span>
- <span data-ttu-id="ef7af-550">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="ef7af-550">**Source of Compromise**</span></span>
- <span data-ttu-id="ef7af-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-551">**Tags**</span></span>

<span data-ttu-id="ef7af-552">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-553">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-554">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-554">**Detection**</span></span>
- <span data-ttu-id="ef7af-555">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-556">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-556">**Direction**</span></span>
- <span data-ttu-id="ef7af-557">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-558">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-559">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-559">**Domain**</span></span>
- <span data-ttu-id="ef7af-560">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-560">**Policy type**</span></span>
- <span data-ttu-id="ef7af-561">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="ef7af-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="ef7af-562">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-562">**Recipients**</span></span>

<span data-ttu-id="ef7af-563">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="ef7af-564">Gegevens weergeven op \> inhoudsmalware</span><span class="sxs-lookup"><span data-stu-id="ef7af-564">View data by Content \> Malware</span></span>

![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="ef7af-566">In de **weergave Gegevens weergeven op \> inhoudsmalware** worden de volgende gegevens weergegeven in de grafiek voor Microsoft Defender voor Office 365 organisaties:</span><span class="sxs-lookup"><span data-stu-id="ef7af-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="ef7af-567">**Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="ef7af-568">**Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="ef7af-569">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-570">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-571">**Locatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-571">**Location**</span></span>
- <span data-ttu-id="ef7af-572">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-572">**Detected by**</span></span>
- <span data-ttu-id="ef7af-573">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-573">**Malware name**</span></span>

<span data-ttu-id="ef7af-574">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-575">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-576">**Detectie:** **Anti-malware-engine** of **Bestandsdetonatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="ef7af-577">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="ef7af-578">Gegevens weergeven op systeem overschrijven</span><span class="sxs-lookup"><span data-stu-id="ef7af-578">View data by System override</span></span>

![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="ef7af-580">In de **weergave Gegevens weergeven op systeem overschrijven** worden de volgende redengegevens overschrijven weergegeven in de grafiek:</span><span class="sxs-lookup"><span data-stu-id="ef7af-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="ef7af-581">**On-premises overslaan**</span><span class="sxs-lookup"><span data-stu-id="ef7af-581">**On-premises skip**</span></span>
- <span data-ttu-id="ef7af-582">**IP-toestaan**</span><span class="sxs-lookup"><span data-stu-id="ef7af-582">**IP allow**</span></span>
- <span data-ttu-id="ef7af-583">**Exchange regel voor e-mailtransport** (regel e-mailstroom)</span><span class="sxs-lookup"><span data-stu-id="ef7af-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="ef7af-584">**Organisatie toegestaan afzenders**</span><span class="sxs-lookup"><span data-stu-id="ef7af-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="ef7af-585">**Toegestane domeinen van de organisatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="ef7af-586">**ZAP niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="ef7af-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="ef7af-587">**Map Ongewenste e-mail niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="ef7af-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="ef7af-588">**Gebruiker Safe afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-588">**User Safe Sender**</span></span>
- <span data-ttu-id="ef7af-589">**User Safe Domain**</span><span class="sxs-lookup"><span data-stu-id="ef7af-589">**User Safe Domain**</span></span>

<span data-ttu-id="ef7af-590">In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="ef7af-591">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-591">**Date**</span></span>
- <span data-ttu-id="ef7af-592">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-592">**Subject**</span></span>
- <span data-ttu-id="ef7af-593">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-593">**Sender**</span></span>
- <span data-ttu-id="ef7af-594">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-594">**Recipients**</span></span>
- <span data-ttu-id="ef7af-595">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-595">**Detected by**</span></span>
- <span data-ttu-id="ef7af-596">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="ef7af-596">**Delivery Status**</span></span>
- <span data-ttu-id="ef7af-597">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="ef7af-597">**Source of Compromise**</span></span>
- <span data-ttu-id="ef7af-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-598">**Tags**</span></span>

<span data-ttu-id="ef7af-599">Als u op **Filter klikt,** zijn de volgende filters beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="ef7af-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="ef7af-600">**Datum**: **Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="ef7af-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="ef7af-601">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-601">**Detection**</span></span>
- <span data-ttu-id="ef7af-602">**Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**</span><span class="sxs-lookup"><span data-stu-id="ef7af-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="ef7af-603">**Richting**</span><span class="sxs-lookup"><span data-stu-id="ef7af-603">**Direction**</span></span>
- <span data-ttu-id="ef7af-604">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="ef7af-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="ef7af-605">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="ef7af-606">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ef7af-606">**Domain**</span></span>
- <span data-ttu-id="ef7af-607">**Beleidstype**</span><span class="sxs-lookup"><span data-stu-id="ef7af-607">**Policy type**</span></span>
- <span data-ttu-id="ef7af-608">**Naam van beleid** (alleen detailstabel)</span><span class="sxs-lookup"><span data-stu-id="ef7af-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="ef7af-609">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-609">**Recipients**</span></span>

<span data-ttu-id="ef7af-610">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ef7af-611"><sup>\*</sup>Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="ef7af-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="ef7af-612">Top malwarerapport</span><span class="sxs-lookup"><span data-stu-id="ef7af-612">Top malware report</span></span>

<span data-ttu-id="ef7af-613">Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="ef7af-614">Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="ef7af-615">Klik **op Top malware** op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="ef7af-616">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Top malware widget on the Email & collaboration reports page](../../media/top-malware-report-widget.png)

<span data-ttu-id="ef7af-618">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="ef7af-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="ef7af-619">Nadat u op **Details weergeven hebt** geklikt, wordt er een grotere versie van het cirkeldiagram weergegeven op de rapportpagina. In de detailtabel onder de grafiek ziet u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="ef7af-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="ef7af-620">**Top malware**</span><span class="sxs-lookup"><span data-stu-id="ef7af-620">**Top malware**</span></span>
- <span data-ttu-id="ef7af-621">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="ef7af-621">**Count**</span></span>

<span data-ttu-id="ef7af-622">Als u op **Filter klikt,** kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="ef7af-624">URL-bedreigingsbeveiligingsrapport</span><span class="sxs-lookup"><span data-stu-id="ef7af-624">URL threat protection report</span></span>

<span data-ttu-id="ef7af-625">Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef7af-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ef7af-626">Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="ef7af-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="ef7af-627">Rapport met gerapporteerde berichten van gebruiker</span><span class="sxs-lookup"><span data-stu-id="ef7af-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef7af-628">Als het rapport **Gerapporteerde** berichten van de gebruiker correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="ef7af-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="ef7af-629">Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef7af-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="ef7af-630">Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="ef7af-631">Het **rapport Gerapporteerde** berichten van gebruiker bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoeging Rapportbericht of de invoeging [Phishing melden.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="ef7af-632">Als u het rapport wilt bekijken in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & samenwerking e-mail & \>  \> **samenwerkingsrapporten** \> **Gebruikers gerapporteerde berichten**.</span><span class="sxs-lookup"><span data-stu-id="ef7af-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="ef7af-633">Klik **op Door gebruiker gerapporteerde** berichten op Details **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="ef7af-634">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="ef7af-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="ef7af-635">Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget met gerapporteerde berichten van gebruiker op de pagina E-mail & samenwerkingsrapporten](../../media/user-reported-messages-widget.png)

<span data-ttu-id="ef7af-637">Nadat u op **Details weergeven** hebt geklikt, kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ef7af-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="ef7af-638">**Datum gerapporteerd:** **Begintijd** en **eindtijd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="ef7af-639">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-639">**Reported by**</span></span>
- <span data-ttu-id="ef7af-640">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-640">**Email subject**</span></span>
- <span data-ttu-id="ef7af-641">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="ef7af-641">**Message reported ID**</span></span>
- <span data-ttu-id="ef7af-642">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="ef7af-642">**Network Message ID**</span></span>
- <span data-ttu-id="ef7af-643">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-643">**Sender**</span></span>
- <span data-ttu-id="ef7af-644">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-644">**Reported reason**</span></span>
  - <span data-ttu-id="ef7af-645">**Geen ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="ef7af-645">**Not junk**</span></span>
  - <span data-ttu-id="ef7af-646">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="ef7af-646">**Phish**</span></span>
  - <span data-ttu-id="ef7af-647">**Spam**</span><span class="sxs-lookup"><span data-stu-id="ef7af-647">**Spam**</span></span>
- <span data-ttu-id="ef7af-648">**Phish-simulatie:** **Ja** of **Nee**</span><span class="sxs-lookup"><span data-stu-id="ef7af-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="ef7af-649">Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**</span><span class="sxs-lookup"><span data-stu-id="ef7af-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="ef7af-650">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="ef7af-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="ef7af-651">**Geen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-651">**None**</span></span>
- <span data-ttu-id="ef7af-652">**Reden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-652">**Reason**</span></span>
- <span data-ttu-id="ef7af-653">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-653">**Sender**</span></span>
- <span data-ttu-id="ef7af-654">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-654">**Reported by**</span></span>
- <span data-ttu-id="ef7af-655">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-655">**Rescan result**</span></span>
- <span data-ttu-id="ef7af-656">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="ef7af-656">**Phish simulation**</span></span>

![Rapport met gerapporteerde berichten van gebruiker](../../media/user-reported-messages-report.png)

<span data-ttu-id="ef7af-658">In de tabel onder de grafiek ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="ef7af-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="ef7af-659">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ef7af-659">**Email subject**</span></span>
- <span data-ttu-id="ef7af-660">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="ef7af-660">**Reported by**</span></span>
- <span data-ttu-id="ef7af-661">**Datum gerapporteerd**</span><span class="sxs-lookup"><span data-stu-id="ef7af-661">**Date reported**</span></span>
- <span data-ttu-id="ef7af-662">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ef7af-662">**Sender**</span></span>
- <span data-ttu-id="ef7af-663">**Gerapporteerde reden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-663">**Reported reason**</span></span>
- <span data-ttu-id="ef7af-664">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="ef7af-664">**Rescan result**</span></span>
- <span data-ttu-id="ef7af-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="ef7af-665">**Tags**</span></span>

<span data-ttu-id="ef7af-666">Als u een bericht wilt verzenden naar Microsoft voor analyse, selecteert u de berichtinvoer in de tabel, klikt u op Verzenden bij **Microsoft** voor analyse en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="ef7af-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="ef7af-667">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="ef7af-667">**Report clean**</span></span>
- <span data-ttu-id="ef7af-668">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="ef7af-668">**Report phishing**</span></span>
- <span data-ttu-id="ef7af-669">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="ef7af-669">**Report malware**</span></span>
- <span data-ttu-id="ef7af-670">**Spam melden**'</span><span class="sxs-lookup"><span data-stu-id="ef7af-670">**Report spam**'</span></span>
- <span data-ttu-id="ef7af-671">**Onderzoek starten** (Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="ef7af-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="ef7af-672">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="ef7af-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="ef7af-673">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:</span><span class="sxs-lookup"><span data-stu-id="ef7af-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="ef7af-674">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="ef7af-674">**Organization Management**</span></span>
- <span data-ttu-id="ef7af-675">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="ef7af-675">**Security Administrator**</span></span>
- <span data-ttu-id="ef7af-676">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="ef7af-676">**Security Reader**</span></span>
- <span data-ttu-id="ef7af-677">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="ef7af-677">**Global Reader**</span></span>

<span data-ttu-id="ef7af-678">Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ef7af-679">**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef7af-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ef7af-680">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef7af-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ef7af-681">Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?</span><span class="sxs-lookup"><span data-stu-id="ef7af-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ef7af-682">Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="ef7af-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ef7af-683">Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="ef7af-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef7af-684">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ef7af-684">Related topics</span></span>

[<span data-ttu-id="ef7af-685">Bescherming tegen spam en anti-malware in EOP</span><span class="sxs-lookup"><span data-stu-id="ef7af-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="ef7af-686">Slimme rapporten en inzichten in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="ef7af-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="ef7af-687">E-mailstroomrapporten weergeven in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="ef7af-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="ef7af-688">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ef7af-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
