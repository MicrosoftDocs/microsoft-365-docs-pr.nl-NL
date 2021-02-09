---
title: Inzichten en rapporten van SMTP-auth-clients in het dashboard van de e-mailstroom
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
description: Beheerders kunnen informatie krijgen over het gebruik van het inzicht smtp-verificatie in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum om e-mail afzenders in hun organisatie te controleren die gebruikmaken van geverifieerde SMTP -verificatie (SMTP AUTH) om e-mailberichten te verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3476ee2f9388245fb105a0910fa7b7d11ec3aeee
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150241"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="57103-103">Inzichten en rapportage van SMTP-auth-clients in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="57103-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="57103-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="57103-104">**Applies to**</span></span>
- [<span data-ttu-id="57103-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="57103-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="57103-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="57103-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="57103-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57103-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="57103-108">Het inzicht van **SMTP Auth-clients** in het dashboard voor de [e-mailstroom](mail-flow-insights-v2.md) en het bijbehorende rapport [SMTP Auth-clients](#smtp-auth-clients-report) in het [beveiligings- & Compliancecentrum](https://protection.office.com) belicht het gebruik van het SMTP AUTH-clientverzendingsprotocol door gebruikers of systeemaccounts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="57103-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="57103-109">Dit oude protocol (dat gebruikmaakt van het eindpunt smtp.office365.com) biedt alleen basisverificatie en is gevoelig voor gebruik door gekromde accounts voor het verzenden van e-mail.</span><span class="sxs-lookup"><span data-stu-id="57103-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="57103-110">Met het inzicht en rapport kunt u controleren op ongebruikelijke activiteiten voor SMTP AUTH-e-mailinzending.</span><span class="sxs-lookup"><span data-stu-id="57103-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="57103-111">Hier worden ook de gebruiksgegevens van TLS voor clients of apparaten met SMTP-AUTH gebruikt.</span><span class="sxs-lookup"><span data-stu-id="57103-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="57103-112">De widget geeft het aantal gebruikers of serviceaccounts aan dat de afgelopen zeven dagen het SMTP-auth-protocol heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="57103-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget SMTP-auth-clients in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="57103-114">Als u op het aantal berichten in de widget klikt, wordt een flyout voor **SMTP-auth-clients** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="57103-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="57103-115">De flyout biedt een samengevoegde weergave van het TLS-gebruik en de volumes van de afgelopen week.</span><span class="sxs-lookup"><span data-stu-id="57103-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Flyout details na klikken op de widget SMTP Auth clients in the Mail flow dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="57103-117">U kunt klikken op de koppeling voor het **rapport SMTP-auth-clients** om naar het rapport SMTP-auth-clients te gaan, zoals wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="57103-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="57103-118">SMTP-verificatierapport voor clients</span><span class="sxs-lookup"><span data-stu-id="57103-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="57103-119">Rapportweergave voor het rapport SMTP-auth-clients</span><span class="sxs-lookup"><span data-stu-id="57103-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="57103-120">Standaard worden in het rapport gegevens van de afgelopen zeven dagen weergegeven, maar de gegevens zijn beschikbaar voor de afgelopen 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="57103-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="57103-121">De sectie Overzicht bevat de volgende grafieken:</span><span class="sxs-lookup"><span data-stu-id="57103-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="57103-122">Gegevens weergeven **op: Volume verzenden:** In de grafiek ziet u standaard het aantal SMTP Auth-clientberichten dat is verzonden vanuit alle domeinen ( Gegevens weergeven **voor:** Alle afzenderdomeinen is standaard geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="57103-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="57103-123">U kunt de resultaten filteren op een  specifiek afzenderdomein door te klikken op Gegevens tonen voor en het domein van de afzender te selecteren in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="57103-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="57103-124">Als u een specifiek gegevenspunt (dag) aanwijzert, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="57103-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Volumeweergave verzenden in het rapport SMTP-auth-clients in het & compliancecentrum](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="57103-126">**Gegevens weergeven met: TLS-gebruik:** in de grafiek ziet u het percentage TLS-gebruik voor alle berichten van de SMTP-auth-client in de geselecteerde periode.</span><span class="sxs-lookup"><span data-stu-id="57103-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="57103-127">In deze grafiek kunt u gebruikers en systeemaccounts identificeren en actie ondernemen die nog steeds oudere versies van TLS gebruiken.</span><span class="sxs-lookup"><span data-stu-id="57103-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Weergave TLS-gebruik in het rapport SMTP-auth-clients in het & compliancecentrum](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="57103-129">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="57103-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="57103-130">Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="57103-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="57103-131">U kunt het datumbereik opgeven en de geadresseerden die het rapport moeten ontvangen.</span><span class="sxs-lookup"><span data-stu-id="57103-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="57103-132">Tabelweergave Details voor het rapport SMTP-auth-clients</span><span class="sxs-lookup"><span data-stu-id="57103-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="57103-133">Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="57103-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="57103-134">**Gegevens weergeven met: Volume verzenden:** de volgende informatie wordt weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="57103-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="57103-135">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="57103-135">**Sender address**</span></span>
  - <span data-ttu-id="57103-136">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="57103-136">**Message count**</span></span>

  <span data-ttu-id="57103-137">Als u een rij selecteert, worden dezelfde details weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="57103-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="57103-138">**Gegevens weergeven met: TLS-gebruik:** de volgende informatie wordt weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="57103-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="57103-139">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="57103-139">**Sender address**</span></span>
  - <span data-ttu-id="57103-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="57103-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="57103-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="57103-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="57103-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="57103-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="57103-143">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="57103-143">**Message count**</span></span>

  <span data-ttu-id="57103-144"><sup>\*</sup> In deze kolom ziet u zowel het percentage als het aantal berichten van de afzender.</span><span class="sxs-lookup"><span data-stu-id="57103-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="57103-145">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="57103-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="57103-146">Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="57103-146">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details uit de detailtabel van de weergave TLS-gebruik in het rapport SMTP Auth-clients](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="57103-148">Klik **op Rapport aanvragen** om een gedetailleerdere versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="57103-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="57103-149">U kunt het datumbereik opgeven en de geadresseerden die het rapport moeten ontvangen.</span><span class="sxs-lookup"><span data-stu-id="57103-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="57103-150">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="57103-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57103-151">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="57103-151">Related topics</span></span>

<span data-ttu-id="57103-152">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="57103-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
