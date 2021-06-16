---
title: E-mailbeveiligingsrapporten weergeven in Microsoft 365 Defender-portal
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
description: Meer informatie over het zoeken en gebruiken van e-mailbeveiligingsrapporten voor uw organisatie. E-mailbeveiligingsrapporten zijn beschikbaar in Microsoft 365 Defender-portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930319"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="658a7-104">E-mailbeveiligingsrapporten weergeven in Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="658a7-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="658a7-105">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="658a7-105">**Applies to**</span></span>
- [<span data-ttu-id="658a7-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="658a7-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="658a7-107">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="658a7-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="658a7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="658a7-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="658a7-109">Er zijn diverse rapporten beschikbaar in de [Microsoft 365 Defender-portal](https://security.microsoft.com) om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie beschermen.</span><span class="sxs-lookup"><span data-stu-id="658a7-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="658a7-110">Als u de benodigde machtigingen [hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten  bekijken in de Microsoft 365 Defender-portal door naar Rapporten \> **e-mail & samenwerking** e-mail- & \> **samenwerkingsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="658a7-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="658a7-111">Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="658a7-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Dashboard Rapporten in de Microsoft 365 Defender-portal](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="658a7-113">Rapport over gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="658a7-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="658a7-114">Dit rapport is beschikbaar in Microsoft 365 organisaties met Exchange Online postvakken.</span><span class="sxs-lookup"><span data-stu-id="658a7-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="658a7-115">Het is niet beschikbaar in zelfstandige Exchange Online Protection (EOP) organisaties.</span><span class="sxs-lookup"><span data-stu-id="658a7-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="658a7-116">In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt.</span><span class="sxs-lookup"><span data-stu-id="658a7-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="658a7-117">Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="658a7-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="658a7-118">Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts.</span><span class="sxs-lookup"><span data-stu-id="658a7-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="658a7-119">Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Voor gecompromitteerde gebruikers in het dashboard Rapporten](../../media/compromised-users-report-widget.png)

<span data-ttu-id="658a7-121">De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="658a7-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="658a7-122">Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten e-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder Gecompromitteerde \>  \>  **gebruikers.** </span><span class="sxs-lookup"><span data-stu-id="658a7-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="658a7-123">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="658a7-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="658a7-124">U kunt zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="658a7-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="658a7-125">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="658a7-126">**Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="658a7-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="658a7-127">**Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.</span><span class="sxs-lookup"><span data-stu-id="658a7-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="658a7-129">Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="658a7-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="658a7-130">**Aanmaaktijd**</span><span class="sxs-lookup"><span data-stu-id="658a7-130">**Creation time**</span></span>
- <span data-ttu-id="658a7-131">**Gebruikers-id**</span><span class="sxs-lookup"><span data-stu-id="658a7-131">**User ID**</span></span>
- <span data-ttu-id="658a7-132">**Actie**</span><span class="sxs-lookup"><span data-stu-id="658a7-132">**Action**</span></span>

<span data-ttu-id="658a7-133">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="658a7-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="658a7-134">Versleutelingsrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-134">Encryption report</span></span>

<span data-ttu-id="658a7-135">Het **versleutelingsrapport** is beschikbaar in EOP (abonnementen met postvakken in Exchange Online zelfstandige EOP zonder Exchange Online postvakken).</span><span class="sxs-lookup"><span data-stu-id="658a7-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="658a7-136">Het beveiligingsteam van uw organisatie kan informatie in dit rapport gebruiken om patronen te identificeren en beleidsregels proactief toe te passen of aan te passen voor gevoelige e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="658a7-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="658a7-137">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="658a7-137">For example:</span></span>

- <span data-ttu-id="658a7-138">Als er een groot aantal e-mailberichten wordt versleuteld door gebruikers, kunt u een versleutelingsbeleid toevoegen om versleuteling voor bepaalde gebruiksgevallen te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="658a7-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="658a7-139">Zie Regels voor e-mailstroom definiëren [om e-mailberichten te](../../compliance/define-mail-flow-rules-to-encrypt-email.md)versleutelen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="658a7-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="658a7-140">Als u een aantal versleutelingssjablonen beschikbaar hebt, maar niemand deze gebruikt, kunt u onderzoeken of gebruikers functietraining nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="658a7-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="658a7-141">Met de statistische weergave kunt u filteren voor de afgelopen 90 dagen, terwijl in de detailweergave 10 dagen kan worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="658a7-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="658a7-142">Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten e-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder \>  \>  **Versleutelingsrapport.** </span><span class="sxs-lookup"><span data-stu-id="658a7-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="658a7-143">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="658a7-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="658a7-144">Zie E-mailversleuteling in Microsoft 365 voor [meer informatie over versleuteling.](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="658a7-145">Rapportweergave voor het versleutelingsrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-145">Report view for the Encryption report</span></span>

<span data-ttu-id="658a7-146">U kunt de volgende filters in de grafiek gebruiken:</span><span class="sxs-lookup"><span data-stu-id="658a7-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="658a7-147">**Gegevens weergeven op: Berichtversleutelingsrapport** en **Afbreed door: Versleutelingsmethode:** De volgende versleutelingsmethoden zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="658a7-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="658a7-148">**Versleuteling door gebruiker**</span><span class="sxs-lookup"><span data-stu-id="658a7-148">**Encryption by user**</span></span>
  - <span data-ttu-id="658a7-149">**Versleuteling per beleid**</span><span class="sxs-lookup"><span data-stu-id="658a7-149">**Encryption by policy**</span></span>

  <span data-ttu-id="658a7-150">Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="658a7-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="658a7-151">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-152">Versleutelingsmethode.</span><span class="sxs-lookup"><span data-stu-id="658a7-152">Encryption method.</span></span>
  - <span data-ttu-id="658a7-153">Versleutelingssjabloon.</span><span class="sxs-lookup"><span data-stu-id="658a7-153">Encryption template.</span></span>

- <span data-ttu-id="658a7-154">**Gegevens weergeven op: Berichtversleutelingsrapport** en **Afbreed door: Versleutelingssjabloon:** De volgende versleutelingsmethoden zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="658a7-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="658a7-155">**Niet doorsturen**</span><span class="sxs-lookup"><span data-stu-id="658a7-155">**Do not forward**</span></span>
  - <span data-ttu-id="658a7-156">**Alleen versleutelen**</span><span class="sxs-lookup"><span data-stu-id="658a7-156">**Encrypt only**</span></span>
  - <span data-ttu-id="658a7-157">**OME vorige**</span><span class="sxs-lookup"><span data-stu-id="658a7-157">**OME previous**</span></span>
  - <span data-ttu-id="658a7-158">**Aangepast**</span><span class="sxs-lookup"><span data-stu-id="658a7-158">**Custom**</span></span>

  <span data-ttu-id="658a7-159">Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="658a7-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="658a7-160">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-161">Versleutelingsmethode</span><span class="sxs-lookup"><span data-stu-id="658a7-161">Encryption method</span></span>
  - <span data-ttu-id="658a7-162">Versleutelingssjabloon</span><span class="sxs-lookup"><span data-stu-id="658a7-162">Encryption template</span></span>

- <span data-ttu-id="658a7-163">**Gegevens weergeven op: Top 5 geadresseerdedomeinen:** In deze weergave ziet u een cirkeldiagram met verzonden berichttellingen voor de bovenste 5 geadresseerdedomeinen.</span><span class="sxs-lookup"><span data-stu-id="658a7-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="658a7-164">Als u op **Filters klikt,** kunt u een **begin-** en **einddatum selecteren.**</span><span class="sxs-lookup"><span data-stu-id="658a7-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="658a7-165">Tabelweergave Details voor het versleutelingsrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="658a7-166">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="658a7-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="658a7-167">**Afbreed door: Versleutelingsmethode** **of Afbreed door: Versleutelingssjabloon:** De volgende informatie wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="658a7-168">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-168">**Date**</span></span>
  - <span data-ttu-id="658a7-169">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-169">**Sender address**</span></span>
  - <span data-ttu-id="658a7-170">**Versleutelingssjabloon**</span><span class="sxs-lookup"><span data-stu-id="658a7-170">**Encryption template**</span></span>
  - <span data-ttu-id="658a7-171">**Versleutelingsmethode**</span><span class="sxs-lookup"><span data-stu-id="658a7-171">**Encryption method**</span></span>
  - <span data-ttu-id="658a7-172">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="658a7-172">**Recipient address**</span></span>
  - <span data-ttu-id="658a7-173">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="658a7-173">**Subject**</span></span>

- <span data-ttu-id="658a7-174">**Gegevens weergeven op: Top 5 adressendomeinen:**</span><span class="sxs-lookup"><span data-stu-id="658a7-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="658a7-175">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-175">**Date**</span></span>
  - <span data-ttu-id="658a7-176">**Domein geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="658a7-176">**Recipient domain**</span></span>
  - <span data-ttu-id="658a7-177">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="658a7-177">**Message count**</span></span>

<span data-ttu-id="658a7-178">Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="658a7-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="658a7-179">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="658a7-180">Versleutelingsmethode</span><span class="sxs-lookup"><span data-stu-id="658a7-180">Encryption method</span></span>
- <span data-ttu-id="658a7-181">Versleutelingssjabloon</span><span class="sxs-lookup"><span data-stu-id="658a7-181">Encryption template</span></span>

<span data-ttu-id="658a7-182">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="658a7-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="658a7-183">E-mailflowstatusrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-183">Mailflow status report</span></span>

<span data-ttu-id="658a7-184">Het **rapport Mailflow-status** bevat informatie over malware, spam, phishing en edge geblokkeerde berichten.</span><span class="sxs-lookup"><span data-stu-id="658a7-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="658a7-185">Zie [Mailflow-statusrapport](view-mail-flow-reports.md#mailflow-status-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="658a7-186">Malwaredetecties in e-mailrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-186">Malware detections in email report</span></span>

<span data-ttu-id="658a7-187">Het **malwaredetectierapport in het** e-mailrapport bevat informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP).</span><span class="sxs-lookup"><span data-stu-id="658a7-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="658a7-188">Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.</span><span class="sxs-lookup"><span data-stu-id="658a7-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="658a7-189">Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.</span><span class="sxs-lookup"><span data-stu-id="658a7-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="658a7-190">Als u het rapport wilt bekijken, opent u  [de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten E-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder Malware gedetecteerd \>  \>  **in e-mail.** </span><span class="sxs-lookup"><span data-stu-id="658a7-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="658a7-191">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="658a7-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Malwaredetecties in e-mailwidget in het dashboard Rapporten](../../media/malware-detections-widget.png)

<span data-ttu-id="658a7-193">U kunt zowel de grafiek als de detailtabel filteren door op **Filters te klikken** en het volgende te selecteren:</span><span class="sxs-lookup"><span data-stu-id="658a7-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="658a7-194">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="658a7-195">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="658a7-195">**Inbound**</span></span>
- <span data-ttu-id="658a7-196">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="658a7-196">**Outbound**</span></span>

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

<span data-ttu-id="658a7-198">Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="658a7-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="658a7-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-199">**Date**</span></span>
- <span data-ttu-id="658a7-200">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-200">**Sender address**</span></span>
- <span data-ttu-id="658a7-201">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="658a7-201">**Recipient address**</span></span>
- <span data-ttu-id="658a7-202">**Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="658a7-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="658a7-203">Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).</span><span class="sxs-lookup"><span data-stu-id="658a7-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="658a7-204">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="658a7-204">**Subject**</span></span>
- <span data-ttu-id="658a7-205">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="658a7-205">**Filename**</span></span>
- <span data-ttu-id="658a7-206">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="658a7-206">**Malware name**</span></span>

<span data-ttu-id="658a7-207">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="658a7-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="658a7-208">E-maillatentierapport</span><span class="sxs-lookup"><span data-stu-id="658a7-208">Mail latency report</span></span>

<span data-ttu-id="658a7-209">Het **rapport E-maillatentie** bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="658a7-210">Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="658a7-211">E-mailrapport verzonden en ontvangen</span><span class="sxs-lookup"><span data-stu-id="658a7-211">Sent and received email report</span></span>

<span data-ttu-id="658a7-212">Het **rapport Verzonden** en ontvangen e-mail bevat informatie over malware, spam, regels voor e-mailstromen (ook wel transportregels genoemd) en geavanceerde malwaredetecties nadat e-mail de service binnenkomt.</span><span class="sxs-lookup"><span data-stu-id="658a7-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="658a7-213">Zie E-mailrapport [verzonden en ontvangen](view-mail-flow-reports.md#sent-and-received-email-report)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="658a7-214">Rapport over spamdetectie</span><span class="sxs-lookup"><span data-stu-id="658a7-214">Spam detections report</span></span>

<span data-ttu-id="658a7-215">In **het rapport Spamdetecties** ziet u spam-e-mailberichten die zijn geblokkeerd door EOP.</span><span class="sxs-lookup"><span data-stu-id="658a7-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="658a7-216">Berichten worden afzonderlijk geteld, niet per geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="658a7-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="658a7-217">Als bijvoorbeeld hetzelfde spambericht is verzonden naar 100 geadresseerden in uw organisatie, telt dit als één bericht.</span><span class="sxs-lookup"><span data-stu-id="658a7-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="658a7-218">In de statistische weergave kan 90 dagen worden gefilterd, terwijl in de detailtabel 10 dagen kan worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="658a7-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="658a7-219">Als u het rapport wilt bekijken, opent u  [de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten E-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder \>  \>  **Spamdetecties.** </span><span class="sxs-lookup"><span data-stu-id="658a7-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="658a7-220">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="658a7-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![Widget Spamdetecties in het dashboard Rapporten](../../media/spam-detections-report-widget.png)

<span data-ttu-id="658a7-222">Zie Bescherming tegen spam in [EOP](anti-spam-protection.md)voor meer informatie over bescherming tegen spam.</span><span class="sxs-lookup"><span data-stu-id="658a7-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="658a7-223">Rapportweergave voor het rapport Spamdetecties</span><span class="sxs-lookup"><span data-stu-id="658a7-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="658a7-224">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="658a7-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="658a7-225">**Afbreed door: Actie**: De volgende gebeurtenistypen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="658a7-226">**Gefilterde spaminhoud**</span><span class="sxs-lookup"><span data-stu-id="658a7-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="658a7-227">**IP-blok spam**</span><span class="sxs-lookup"><span data-stu-id="658a7-227">**Spam IP block**</span></span>
  - <span data-ttu-id="658a7-228">**Spam envelopblok**</span><span class="sxs-lookup"><span data-stu-id="658a7-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="658a7-229">**Spam DBEB-filter:** Directory based edge blocking (DBEB)</span><span class="sxs-lookup"><span data-stu-id="658a7-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="658a7-230">Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel items die dag zijn geblokkeerd en hoe deze items zijn gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="658a7-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Actieweergave in het rapport Spamdetecties](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="658a7-232">**Afbreed door: Richting**: De volgende aanwijzingen worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="658a7-233">**Binnenkomende**</span><span class="sxs-lookup"><span data-stu-id="658a7-233">**Inbound**</span></span>
  - <span data-ttu-id="658a7-234">**Uitgaande**</span><span class="sxs-lookup"><span data-stu-id="658a7-234">**Outbound**</span></span>

  ![Richtingsweergave in het rapport Spamdetecties](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="658a7-236">Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="658a7-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="658a7-237">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="658a7-238">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="658a7-238">Direction values</span></span>
- <span data-ttu-id="658a7-239">Waarden voor gebeurtenistype</span><span class="sxs-lookup"><span data-stu-id="658a7-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="658a7-240">Tabelweergave details voor het rapport Spamdetecties</span><span class="sxs-lookup"><span data-stu-id="658a7-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="658a7-241">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="658a7-242">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-242">**Date**</span></span>
- <span data-ttu-id="658a7-243">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-243">**Sender address**</span></span>
- <span data-ttu-id="658a7-244">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="658a7-244">**Recipient address**</span></span>
- <span data-ttu-id="658a7-245">**Gebeurtenistype**</span><span class="sxs-lookup"><span data-stu-id="658a7-245">**Event type**</span></span>
- <span data-ttu-id="658a7-246">**Actie**</span><span class="sxs-lookup"><span data-stu-id="658a7-246">**Action**</span></span>
- <span data-ttu-id="658a7-247">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="658a7-247">**Subject**</span></span>

<span data-ttu-id="658a7-248">Als u in een **detailtabel** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="658a7-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="658a7-249">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="658a7-250">Richtingswaarden</span><span class="sxs-lookup"><span data-stu-id="658a7-250">Direction values</span></span>
- <span data-ttu-id="658a7-251">Waarden voor gebeurtenistype</span><span class="sxs-lookup"><span data-stu-id="658a7-251">Event type values</span></span>

<span data-ttu-id="658a7-252">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="658a7-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="658a7-253">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="658a7-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="658a7-254">Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties.</span><span class="sxs-lookup"><span data-stu-id="658a7-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="658a7-255">In de oudere versie van het rapport werden alleen **Goede e-mail en** **Als spam gesnapt.**</span><span class="sxs-lookup"><span data-stu-id="658a7-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="658a7-256">Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing.</span><span class="sxs-lookup"><span data-stu-id="658a7-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="658a7-257">Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="658a7-258">Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.</span><span class="sxs-lookup"><span data-stu-id="658a7-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="658a7-259"><sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.</span><span class="sxs-lookup"><span data-stu-id="658a7-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="658a7-260">Als u het rapport wilt bekijken, opent u  [de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten e-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder \>  \>  **Spoofdetecties.** </span><span class="sxs-lookup"><span data-stu-id="658a7-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="658a7-261">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="658a7-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![Widget Spoofdetecties in het dashboard Rapporten](../../media/spoof-detections-widget.png)

<span data-ttu-id="658a7-263">Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.</span><span class="sxs-lookup"><span data-stu-id="658a7-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="658a7-264">U kunt zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:</span><span class="sxs-lookup"><span data-stu-id="658a7-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="658a7-265">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="658a7-266">**Result**</span><span class="sxs-lookup"><span data-stu-id="658a7-266">**Result**</span></span>
  - <span data-ttu-id="658a7-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="658a7-267">**Pass**</span></span>
  - <span data-ttu-id="658a7-268">**Mislukken**</span><span class="sxs-lookup"><span data-stu-id="658a7-268">**Fail**</span></span>
  - <span data-ttu-id="658a7-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="658a7-269">**SoftPass**</span></span>
  - <span data-ttu-id="658a7-270">**Geen**</span><span class="sxs-lookup"><span data-stu-id="658a7-270">**None**</span></span>
  - <span data-ttu-id="658a7-271">**Overige**</span><span class="sxs-lookup"><span data-stu-id="658a7-271">**Other**</span></span>

- <span data-ttu-id="658a7-272">**Spooftype:** **Intern** en **Extern**</span><span class="sxs-lookup"><span data-stu-id="658a7-272">**Spoof type**: **Internal** and **External**</span></span>

![Rapportweergave in het rapport Spoofdetecties](../../media/spoof-detections-report-view.png)

<span data-ttu-id="658a7-274">Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="658a7-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="658a7-275">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-275">**Date**</span></span>
- <span data-ttu-id="658a7-276">**Vervalste gebruiker**</span><span class="sxs-lookup"><span data-stu-id="658a7-276">**Spoofed user**</span></span>
- <span data-ttu-id="658a7-277">**Verzendende infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="658a7-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="658a7-278">**Spooftype**</span><span class="sxs-lookup"><span data-stu-id="658a7-278">**Spoof type**</span></span>
- <span data-ttu-id="658a7-279">**Result**</span><span class="sxs-lookup"><span data-stu-id="658a7-279">**Result**</span></span>
- <span data-ttu-id="658a7-280">**Resultaatcode**</span><span class="sxs-lookup"><span data-stu-id="658a7-280">**Result code**</span></span>
- <span data-ttu-id="658a7-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="658a7-281">**SPF**</span></span>
- <span data-ttu-id="658a7-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="658a7-282">**DKIM**</span></span>
- <span data-ttu-id="658a7-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="658a7-283">**DMARC**</span></span>
- <span data-ttu-id="658a7-284">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="658a7-284">**Message count**</span></span>

<span data-ttu-id="658a7-285">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="658a7-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="658a7-286">Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="658a7-287">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="658a7-287">Threat protection status report</span></span>

<span data-ttu-id="658a7-288">Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Microsoft Defender voor Office 365; De rapporten bevatten echter verschillende gegevens.</span><span class="sxs-lookup"><span data-stu-id="658a7-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="658a7-289">EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="658a7-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="658a7-290">Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische [nul-uursre](safe-attachments.md) [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md)Safe Bijlagen en [Anti-phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="658a7-291">U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="658a7-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="658a7-292">**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.</span><span class="sxs-lookup"><span data-stu-id="658a7-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="658a7-293">Als u het rapport wilt bekijken, opent u  [de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten e-mail & samenwerking e-mail & samenwerkingsrapporten en klikt u op Details weergeven onder Status \>  \>  **bedreigingsbeveiliging.** </span><span class="sxs-lookup"><span data-stu-id="658a7-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="658a7-294">Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:</span><span class="sxs-lookup"><span data-stu-id="658a7-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="658a7-295">Microsoft Defender voor Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="658a7-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="658a7-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="658a7-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Statuswidget bedreigingsbeveiliging in het dashboard Rapporten](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="658a7-298">Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="658a7-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="658a7-299">Als u op **Filters** klikt, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen worden beperkt tot 30 dagen).</span><span class="sxs-lookup"><span data-stu-id="658a7-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="658a7-300">In de tabelweergave details kunt u 30 dagen filteren.</span><span class="sxs-lookup"><span data-stu-id="658a7-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="658a7-301">Rapportweergave voor het rapport Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="658a7-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="658a7-302">De volgende weergaven zijn beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="658a7-302">The following views are available:</span></span>

- <span data-ttu-id="658a7-303">**Gegevens weergeven door: Overzicht:** De volgende detectiegegevens worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="658a7-304">**E-mailmalware**</span><span class="sxs-lookup"><span data-stu-id="658a7-304">**Email malware**</span></span>
  - <span data-ttu-id="658a7-305">**E-mail phish**</span><span class="sxs-lookup"><span data-stu-id="658a7-305">**Email phish**</span></span>
  - <span data-ttu-id="658a7-306">**Inhoudsmalware**</span><span class="sxs-lookup"><span data-stu-id="658a7-306">**Content malware**</span></span>

  ![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="658a7-308">**Gegevens weergeven op: Inhoud \> Malware**<sup>1:</sup>De volgende informatie wordt weergegeven voor Microsoft Defender voor Office 365 organisaties:</span><span class="sxs-lookup"><span data-stu-id="658a7-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="658a7-309">**Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="658a7-310">**Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="658a7-312">**Gegevens weergeven op: Bericht overschrijven:** De volgende redengegevens worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="658a7-313">**On-premises overslaan**</span><span class="sxs-lookup"><span data-stu-id="658a7-313">**On-premises skip**</span></span>
  - <span data-ttu-id="658a7-314">**IP-toestaan**</span><span class="sxs-lookup"><span data-stu-id="658a7-314">**IP Allow**</span></span>
  - <span data-ttu-id="658a7-315">**E-mailstroomregel**</span><span class="sxs-lookup"><span data-stu-id="658a7-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="658a7-316">**Afzender toestaan**</span><span class="sxs-lookup"><span data-stu-id="658a7-316">**Sender allow**</span></span>
  - <span data-ttu-id="658a7-317">**Domein toestaan**</span><span class="sxs-lookup"><span data-stu-id="658a7-317">**Domain allow**</span></span>
  - <span data-ttu-id="658a7-318">**ZAP niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="658a7-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="658a7-319">**Map Ongewenste e-mail niet ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="658a7-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="658a7-320">**Gebruiker Safe afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="658a7-321">**User Safe Domain**</span><span class="sxs-lookup"><span data-stu-id="658a7-321">**User Safe Domain**</span></span>

  ![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="658a7-323">**Afbreed door: Detectietechnologie en** **Gegevens weergeven door: E-mail \> phish:** De volgende informatie wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="658a7-324">**ATP-gegenereerde URL-reputatie**<sup>1:</sup>Kwaadaardige URL-reputatie die is gegenereerd met Defender voor Office 365-detonaties in andere Microsoft 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="658a7-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="658a7-325">**Geavanceerd phish-filter:** Phishing-signalen op basis van machine learning.</span><span class="sxs-lookup"><span data-stu-id="658a7-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="658a7-326">**Anti-spoof - DMARC-fout:** DMARC-verificatiefout op berichten.</span><span class="sxs-lookup"><span data-stu-id="658a7-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="658a7-327">**Anti-spoof - intra-org**: Afzender probeert het domein van de geadresseerde te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="658a7-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="658a7-328">**Anti-spoof - extern domein:** Afzender probeert een ander domein te vervalsen.</span><span class="sxs-lookup"><span data-stu-id="658a7-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="658a7-329">**Merk imitatie:** Imitatie van bekende merken op basis van afzenders.</span><span class="sxs-lookup"><span data-stu-id="658a7-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="658a7-330">**Domein imitatie**<sup>1:</sup>Imitatie van domeinen die de klant bezit of definieert.</span><span class="sxs-lookup"><span data-stu-id="658a7-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="658a7-331">**EOP URL-reputatie:** reputatie van schadelijke URL's.</span><span class="sxs-lookup"><span data-stu-id="658a7-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="658a7-332">**Algemeen phish-filter:** Phishing-signalen op basis van analistregels.</span><span class="sxs-lookup"><span data-stu-id="658a7-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="658a7-333">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="658a7-333">**Others**</span></span>
  - <span data-ttu-id="658a7-334">**Phish ZAP**<sup>2:</sup>Automatische nuluurse purge van phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="658a7-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="658a7-335">**URL-detonatie**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="658a7-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="658a7-336">**Gebruikers-imitatie**<sup>1:</sup>imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="658a7-338">**Afbreed door: Detectietechnologie en** **Gegevens weergeven door: E-mail \> malware:** De volgende informatie wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="658a7-339">**ATP-gegenereerde**<sup>bestandsreputatie 1:</sup>Alle schadelijke bestandsreputatie die door Defender wordt gegenereerd voor Office 365 detonaties.</span><span class="sxs-lookup"><span data-stu-id="658a7-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="658a7-340">**Anti-malware engine**<sup>1:</sup>Detectie van anti-malware-engines.</span><span class="sxs-lookup"><span data-stu-id="658a7-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="658a7-341">**Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="658a7-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="658a7-342">**Bestandsdetonatie**<sup>1</sup>: Detectie door Safe bijlagen.</span><span class="sxs-lookup"><span data-stu-id="658a7-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="658a7-343">**Schadelijke bestandsreputatie**</span><span class="sxs-lookup"><span data-stu-id="658a7-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="658a7-344">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="658a7-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="658a7-345">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="658a7-345">**Others**</span></span>

  ![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="658a7-347">**Afbreed door: Type beleid** en **Gegevens weergeven op: E-mail \> Phish** of Gegevens weergeven **door: \> E-mail malware:** De volgende informatie wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="658a7-348">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="658a7-348">**Anti-malware**</span></span>
  - <span data-ttu-id="658a7-349">**Safe Bijlagen**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="658a7-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="658a7-350">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="658a7-350">**Anti-phish**</span></span>
  - <span data-ttu-id="658a7-351">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="658a7-351">**Anti-spam**</span></span>
  - <span data-ttu-id="658a7-352">**E-mailstroomregel** (ook wel transportregel genoemd)</span><span class="sxs-lookup"><span data-stu-id="658a7-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="658a7-353">**Anderen**</span><span class="sxs-lookup"><span data-stu-id="658a7-353">**Others**</span></span>

  ![Weergave beleidtype voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="658a7-355">**Afbreed door: Bezorgingsstatus** en **Gegevens weergeven door: E-mail \> Phish** of Gegevens weergeven **door: \> E-mail malware:** De volgende informatie wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="658a7-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="658a7-356">**Bezorging mislukt**</span><span class="sxs-lookup"><span data-stu-id="658a7-356">**Delivery failed**</span></span>
  - <span data-ttu-id="658a7-357">**Laten vallen**</span><span class="sxs-lookup"><span data-stu-id="658a7-357">**Dropped**</span></span>
  - <span data-ttu-id="658a7-358">**Doorgestuurd**</span><span class="sxs-lookup"><span data-stu-id="658a7-358">**Forwarded**</span></span>
  - <span data-ttu-id="658a7-359">**Gehost postvak: aangepaste map**</span><span class="sxs-lookup"><span data-stu-id="658a7-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="658a7-360">**Gehost postvak: Verwijderde items**</span><span class="sxs-lookup"><span data-stu-id="658a7-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="658a7-361">**Gehost postvak: Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="658a7-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="658a7-362">**Gehost postvak: Ongewenste e-mail**</span><span class="sxs-lookup"><span data-stu-id="658a7-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="658a7-363">**On-premises server: geleverd**</span><span class="sxs-lookup"><span data-stu-id="658a7-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="658a7-364">**Quarantaine**</span><span class="sxs-lookup"><span data-stu-id="658a7-364">**Quarantine**</span></span>

  ![Weergave bezorgingsstatus voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="658a7-366"><sup>1</sup> Defender voor Office 365 alleen</span><span class="sxs-lookup"><span data-stu-id="658a7-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="658a7-367"><sup>2</sup> Zap (Zero Hour Auto Purge) is niet beschikbaar in zelfstandige EOP (het werkt alleen in Exchange Online postvakken).</span><span class="sxs-lookup"><span data-stu-id="658a7-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="658a7-368">Als u op **Filters klikt,** zijn de beschikbare filters afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="658a7-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="658a7-369">Voor **Gegevens weergeven op: Content \> Malware**, kunt u het rapport wijzigen op **begindatum** en **einddatum** en de **detectiewaarde.**</span><span class="sxs-lookup"><span data-stu-id="658a7-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="658a7-370">Voor **Gegevens weergeven door: Bericht overschrijven,** kunt u het rapport wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="658a7-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="658a7-371">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-372">**Reden overschrijven**</span><span class="sxs-lookup"><span data-stu-id="658a7-372">**Override Reason**</span></span>
  - <span data-ttu-id="658a7-373">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="658a7-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="658a7-374">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="658a7-375">**Domein**</span><span class="sxs-lookup"><span data-stu-id="658a7-375">**Domain**</span></span>

- <span data-ttu-id="658a7-376">Voor alle andere weergaven kunt u het rapport wijzigen met de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="658a7-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="658a7-377">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-378">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="658a7-378">**Detection**</span></span>
  - <span data-ttu-id="658a7-379">**Beveiligd door**: **ATP** of **EOP**</span><span class="sxs-lookup"><span data-stu-id="658a7-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="658a7-380">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="658a7-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="658a7-381">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="658a7-382">**Domein**</span><span class="sxs-lookup"><span data-stu-id="658a7-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="658a7-383">Tabelweergave details voor het rapport Status van bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="658a7-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="658a7-384">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="658a7-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="658a7-385">**Gegevens weergeven door: Overzicht:** **Knop Details weergeven** is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="658a7-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="658a7-386">**Gegevens weergeven op: Inhoud \> Malware:**</span><span class="sxs-lookup"><span data-stu-id="658a7-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="658a7-387">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-387">**Date**</span></span>
  - <span data-ttu-id="658a7-388">**Locatie**</span><span class="sxs-lookup"><span data-stu-id="658a7-388">**Location**</span></span>
  - <span data-ttu-id="658a7-389">**Aangestuurd door**</span><span class="sxs-lookup"><span data-stu-id="658a7-389">**Directed by**</span></span>
  - <span data-ttu-id="658a7-390">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="658a7-390">**Malware name**</span></span>

  <span data-ttu-id="658a7-391">Als u in deze weergave op **Filters** klikt, kunt u het rapport wijzigen op **Begindatum** **en** Einddatum en de **waarde Detectie.**</span><span class="sxs-lookup"><span data-stu-id="658a7-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="658a7-392">**Gegevens weergeven op: Bericht overschrijven:**</span><span class="sxs-lookup"><span data-stu-id="658a7-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="658a7-393">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-393">**Date**</span></span>
  - <span data-ttu-id="658a7-394">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="658a7-394">**Subject**</span></span>
  - <span data-ttu-id="658a7-395">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-395">**Sender**</span></span>
  - <span data-ttu-id="658a7-396">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="658a7-396">**Recipients**</span></span>
  - <span data-ttu-id="658a7-397">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="658a7-397">**Detected by**</span></span>
  - <span data-ttu-id="658a7-398">**Reden overschrijven**</span><span class="sxs-lookup"><span data-stu-id="658a7-398">**Override Reason**</span></span>
  - <span data-ttu-id="658a7-399">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="658a7-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="658a7-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="658a7-400">**Tags**</span></span>

  <span data-ttu-id="658a7-401">Als u in deze **weergave op Filters** klikt, kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="658a7-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="658a7-402">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-403">**Reden overschrijven**</span><span class="sxs-lookup"><span data-stu-id="658a7-403">**Override Reason**</span></span>
  - <span data-ttu-id="658a7-404">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="658a7-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="658a7-405">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="658a7-406">**Domein**</span><span class="sxs-lookup"><span data-stu-id="658a7-406">**Domain**</span></span>
  - <span data-ttu-id="658a7-407">**Geadresseerden** (Houd er rekening mee dat deze filterbare eigenschap alleen beschikbaar is in de tabelweergave details)</span><span class="sxs-lookup"><span data-stu-id="658a7-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="658a7-408">Alle andere grafieken:</span><span class="sxs-lookup"><span data-stu-id="658a7-408">All other charts:</span></span>

  - <span data-ttu-id="658a7-409">**Datum**</span><span class="sxs-lookup"><span data-stu-id="658a7-409">**Date**</span></span>
  - <span data-ttu-id="658a7-410">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="658a7-410">**Subject**</span></span>
  - <span data-ttu-id="658a7-411">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="658a7-411">**Sender**</span></span>
  - <span data-ttu-id="658a7-412">**Geadresseerden**</span><span class="sxs-lookup"><span data-stu-id="658a7-412">**Recipients**</span></span>
  - <span data-ttu-id="658a7-413">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="658a7-413">**Detected by**</span></span>
  - <span data-ttu-id="658a7-414">**Bezorgingsstatus**</span><span class="sxs-lookup"><span data-stu-id="658a7-414">**Delivery Status**</span></span>
  - <span data-ttu-id="658a7-415">**Bron van compromis**</span><span class="sxs-lookup"><span data-stu-id="658a7-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="658a7-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="658a7-416">**Tags**</span></span>

  <span data-ttu-id="658a7-417">Als u op **Filters klikt,** kunt u het rapport met de volgende filters wijzigen:</span><span class="sxs-lookup"><span data-stu-id="658a7-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="658a7-418">**Begindatum** en **einddatum**</span><span class="sxs-lookup"><span data-stu-id="658a7-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="658a7-419">**Detectie**</span><span class="sxs-lookup"><span data-stu-id="658a7-419">**Detection**</span></span>
  - <span data-ttu-id="658a7-420">**Beveiligd door**: **Defender voor Office 365** of **EOP**</span><span class="sxs-lookup"><span data-stu-id="658a7-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="658a7-421">**Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts).</span><span class="sxs-lookup"><span data-stu-id="658a7-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="658a7-422">Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="658a7-423">**Domein**</span><span class="sxs-lookup"><span data-stu-id="658a7-423">**Domain**</span></span>
  - <span data-ttu-id="658a7-424">**Geadresseerden** (Houd er rekening mee dat deze filterbare eigenschap alleen beschikbaar is in de tabelweergave details)</span><span class="sxs-lookup"><span data-stu-id="658a7-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="658a7-425">Top malwarerapport</span><span class="sxs-lookup"><span data-stu-id="658a7-425">Top malware report</span></span>

<span data-ttu-id="658a7-426">Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="658a7-427">Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender-portal,](https://security.microsoft.com)gaat u naar Rapporten E-mail & samenwerking e-mail \>  \> **& samenwerkingsrapporten**  en klikt u op Details weergeven onder **Top malware.**</span><span class="sxs-lookup"><span data-stu-id="658a7-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="658a7-428">Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="658a7-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![De belangrijkste malwarewidget in het dashboard Rapporten](../../media/top-malware-report-widget.png)

<span data-ttu-id="658a7-430">Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.</span><span class="sxs-lookup"><span data-stu-id="658a7-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

<span data-ttu-id="658a7-432">Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:</span><span class="sxs-lookup"><span data-stu-id="658a7-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="658a7-433">**Top malware**</span><span class="sxs-lookup"><span data-stu-id="658a7-433">**Top malware**</span></span>
- <span data-ttu-id="658a7-434">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="658a7-434">**Count**</span></span>

<span data-ttu-id="658a7-435">Als u in **de rapportweergave** of detailtabelweergave op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="658a7-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="658a7-436">URL-bedreigingsbeveiligingsrapport</span><span class="sxs-lookup"><span data-stu-id="658a7-436">URL threat protection report</span></span>

<span data-ttu-id="658a7-437">Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="658a7-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="658a7-438">Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="658a7-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="658a7-439">Rapport met gerapporteerde berichten van gebruiker</span><span class="sxs-lookup"><span data-stu-id="658a7-439">User reported messages report</span></span>

<span data-ttu-id="658a7-440">Het **rapport Gerapporteerde** berichten van gebruiker bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoeging Rapportbericht of de invoegmap [Rapport phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="658a7-441">Details zijn beschikbaar voor elk bericht, inclusief de bezorgingsreden, een dergelijke uitzondering voor spambeleid of e-mailstroomregel die is geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="658a7-442">Als u details wilt weergeven, selecteert u een item in de  lijst met gebruikersrapporten en bekijkt u de gegevens op de tabbladen Overzicht **en** Details.</span><span class="sxs-lookup"><span data-stu-id="658a7-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![In het rapport Gerapporteerde berichten van gebruiker ziet u berichten die gebruikers hebben gelabeld als ongewenste e-mail, geen ongewenste e-mail of phishingpogingen.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="658a7-444">Als u dit rapport wilt bekijken, gaat u  in [Microsoft 365 Defender-portal](https://security.microsoft.com)naar Rapporten e-mail & samenwerking e-mail & \>  \> **samenwerkingsrapporten** \> **Gebruikers gerapporteerde berichten**.</span><span class="sxs-lookup"><span data-stu-id="658a7-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="658a7-445">Ga naar **Rapporten** \> **E-mail & samenwerking** \> **e-mail & samenwerkingsrapporten** Gebruiker \> **gerapporteerde berichten**.</span><span class="sxs-lookup"><span data-stu-id="658a7-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![Kies in Microsoft 365 Defender-portal Rapporten \> e-mail & samenwerking e-mail- & \> samenwerkingsrapporten \> Gebruiker gerapporteerde berichten](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="658a7-447">Als het rapport Gerapporteerde berichten van de gebruiker correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Office 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="658a7-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="658a7-448">Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="658a7-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="658a7-449">Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="658a7-450">Welke machtigingen zijn nodig om deze rapporten weer te geven?</span><span class="sxs-lookup"><span data-stu-id="658a7-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="658a7-451">Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender-portal:</span><span class="sxs-lookup"><span data-stu-id="658a7-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="658a7-452">**Organisatiebeheer**</span><span class="sxs-lookup"><span data-stu-id="658a7-452">**Organization Management**</span></span>
- <span data-ttu-id="658a7-453">**Beveiligingsbeheerder**</span><span class="sxs-lookup"><span data-stu-id="658a7-453">**Security Administrator**</span></span>
- <span data-ttu-id="658a7-454">**Beveiligingslezer**</span><span class="sxs-lookup"><span data-stu-id="658a7-454">**Security Reader**</span></span>
- <span data-ttu-id="658a7-455">**Globale lezer**</span><span class="sxs-lookup"><span data-stu-id="658a7-455">**Global Reader**</span></span>

<span data-ttu-id="658a7-456">Zie Machtigingen [in de portal Microsoft 365 Defender voor meer informatie.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="658a7-457">**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de vereiste  machtigingen in de Microsoft 365 Defender-portal en machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="658a7-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="658a7-458">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="658a7-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="658a7-459">Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?</span><span class="sxs-lookup"><span data-stu-id="658a7-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="658a7-460">Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="658a7-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="658a7-461">Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="658a7-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="658a7-462">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="658a7-462">Related topics</span></span>

[<span data-ttu-id="658a7-463">Bescherming tegen spam en anti-malware in EOP</span><span class="sxs-lookup"><span data-stu-id="658a7-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="658a7-464">Slimme rapporten en inzichten in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="658a7-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="658a7-465">E-mailstroomrapporten weergeven in Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="658a7-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="658a7-466">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="658a7-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
