---
title: Inzicht en rapport van SMTP Auth-clients in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze het SMTP Auth-inzicht en rapport kunnen gebruiken in het dashboard E-mailstroom in het beveiligings- & compliancecentrum om e-mail afzenders in hun organisatie te controleren die geverifieerde SMTP (SMTP AUTH) gebruiken om e-mailberichten te verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a979f0e80fc303868bf2572974563323035fc4bc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204129"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="6dee1-103">Inzicht en rapport van SMTP Auth-clients in het Beveiligings- & Compliance center</span><span class="sxs-lookup"><span data-stu-id="6dee1-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6dee1-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="6dee1-104">**Applies to**</span></span>
- [<span data-ttu-id="6dee1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6dee1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6dee1-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6dee1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6dee1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6dee1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6dee1-108">De **SMTP Auth-clients** in het [dashboard Mail flow](mail-flow-insights-v2.md) en het bijbehorende RAPPORT [SMTP Auth-clients](#smtp-auth-clients-report) in het [Beveiligings- & Compliancecentrum](https://protection.office.com) markeren het gebruik van het SMTP AUTH-clientverzendingsprotocol door gebruikers of systeemaccounts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6dee1-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="6dee1-109">Dit oudere protocol (dat gebruikmaakt van het eindpunt smtp.office365.com) biedt alleen basisverificatie en is vatbaar voor gebruik door gecompromitteerde accounts om e-mail te verzenden.</span><span class="sxs-lookup"><span data-stu-id="6dee1-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="6dee1-110">Met het inzicht en rapport kunt u controleren op ongebruikelijke activiteiten voor SMTP AUTH-e-mailinzendingen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="6dee1-111">Hier worden ook de TLS-gebruiksgegevens voor clients of apparaten met SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="6dee1-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="6dee1-112">De widget geeft het aantal gebruikers of serviceaccounts aan dat de afgelopen 7 dagen het SMTP Auth-protocol heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6dee1-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP Auth-clients widget in het e-mailstroomdashboard in & Compliance center](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="6dee1-114">Als u op het aantal berichten in de widget klikt, wordt er een flyout voor **SMTP Auth-clients** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6dee1-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="6dee1-115">De flyout biedt een samengevoegde weergave van het TLS-gebruik en de volumes van de afgelopen week.</span><span class="sxs-lookup"><span data-stu-id="6dee1-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Details flyout after clicking on the SMTP Auth clients widget in the Mail flow dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="6dee1-117">U kunt op de **koppeling SMTP Auth-clientsrapport** klikken om naar het rapport SMTP Auth-clients te gaan, zoals wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="6dee1-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="6dee1-118">SMTP-verificatierapport voor clients</span><span class="sxs-lookup"><span data-stu-id="6dee1-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="6dee1-119">Rapportweergave voor het rapport SMTP Auth-clients</span><span class="sxs-lookup"><span data-stu-id="6dee1-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="6dee1-120">Standaard worden in het rapport gegevens van de afgelopen 7 dagen weergegeven, maar gegevens zijn beschikbaar voor de afgelopen 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="6dee1-121">De overzichtssectie bevat de volgende grafieken:</span><span class="sxs-lookup"><span data-stu-id="6dee1-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="6dee1-122">**Gegevens weergeven door:** Volume verzenden: Standaard wordt in de grafiek het aantal SMTP Auth-clientberichten weergegeven dat vanuit alle domeinen is verzonden ( Gegevens weergeven **voor:** Alle afzenderdomeinen is standaard geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="6dee1-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="6dee1-123">U kunt de resultaten filteren op een specifiek afzenderdomein door te klikken op **Gegevens** voor en het afzenderdomein in de vervolgkeuzelijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6dee1-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="6dee1-124">Als u een bepaald gegevenspunt (dag) met de muisaanwijzer beweegt, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6dee1-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Volumeweergave verzenden in het rapport SMTP Auth-clients in het beveiligings- & compliancecentrum](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="6dee1-126">**Gegevens weergeven op: TLS-gebruik:** In de grafiek ziet u het percentage TLS-gebruik voor alle SMTP Auth-clientberichten gedurende de geselecteerde periode.</span><span class="sxs-lookup"><span data-stu-id="6dee1-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="6dee1-127">Met deze grafiek kunt u gebruikers en systeemaccounts identificeren en actie ondernemen die nog steeds oudere versies van TLS gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6dee1-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![TLS-gebruiksweergave in het rapport SMTP Auth-clients in het beveiligings- & Compliancecentrum](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="6dee1-129">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="6dee1-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6dee1-130">Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="6dee1-131">U kunt het datumbereik en de geadresseerden opgeven om het rapport te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="6dee1-132">Tabelweergave details voor het rapport SMTP Auth-clients</span><span class="sxs-lookup"><span data-stu-id="6dee1-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="6dee1-133">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="6dee1-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6dee1-134">**Gegevens weergeven door: Volume verzenden:** De volgende gegevens worden weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="6dee1-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="6dee1-135">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="6dee1-135">**Sender address**</span></span>
  - <span data-ttu-id="6dee1-136">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="6dee1-136">**Message count**</span></span>

  <span data-ttu-id="6dee1-137">Als u een rij selecteert, worden dezelfde details weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="6dee1-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="6dee1-138">**Gegevens weergeven op: TLS-gebruik:** De volgende gegevens worden weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="6dee1-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="6dee1-139">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="6dee1-139">**Sender address**</span></span>
  - <span data-ttu-id="6dee1-140">**TLS1,0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6dee1-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="6dee1-141">**TLS1,1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6dee1-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="6dee1-142">**TLS1,2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6dee1-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="6dee1-143">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="6dee1-143">**Message count**</span></span>

  <span data-ttu-id="6dee1-144"><sup>\*</sup> In deze kolom ziet u het percentage en het aantal berichten van de afzender.</span><span class="sxs-lookup"><span data-stu-id="6dee1-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="6dee1-145">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="6dee1-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6dee1-146">Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="6dee1-146">If you select a row, similar details are shown in a flyout:</span></span>

![Details flyout from the details table of the TLS usage view in the SMTP Auth clients report](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="6dee1-148">Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="6dee1-149">U kunt het datumbereik en de geadresseerden opgeven om het rapport te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6dee1-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="6dee1-150">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="6dee1-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6dee1-151">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6dee1-151">Related topics</span></span>

<span data-ttu-id="6dee1-152">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="6dee1-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
