---
title: Inzicht en rapporten met SMTP-verificatie clients in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het SMTP-authenticatie inzicht en rapporten kunt gebruiken in het dashboard voor de beveiliging van de e-mail in het beveiligings & nalevings centrum om e-mail afzenders in hun organisatie met geverifieerde SMTP-verificatie (SMTP-verificatie) te controleren en e-mailberichten te verzenden.
ms.openlocfilehash: 4123edcfa08e31217dcd6a29186492bc036fa7a0
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357432"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="ffbec-103">Client-auth-clients inzicht en rapporteren in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="ffbec-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="ffbec-104">De **SMTP auth-clients** bieden inzicht in in het [Dashboard voor de e-mail stroom](mail-flow-insights-v2.md) en het bijbehorende [SMTP-](#smtp-auth-clients-report) auth-client rapport in het [nalevings centrum voor beveiligings &](https://protection.office.com) het gebruik van het SMTP-verificatieprotocol voor clientverificatie door gebruikers of systeemaccounts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ffbec-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="ffbec-105">Dit oudere protocol (met het eindpunt smtp.office365.com) biedt alleen basisverificatie en kan worden gebruikt door gemanipuleerde accounts om e-mail te verzenden.</span><span class="sxs-lookup"><span data-stu-id="ffbec-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="ffbec-106">In het inzicht en de rapportage kunt u controleren op ongebruikelijke activiteiten voor e-mail inzendingen van SMTP-verificatie.</span><span class="sxs-lookup"><span data-stu-id="ffbec-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="ffbec-107">Ook de TLS-gebruiksgegevens voor clients of apparaten worden weergegeven met SMTP-AUTH.</span><span class="sxs-lookup"><span data-stu-id="ffbec-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="ffbec-108">De widget geeft het aantal gebruikers of serviceaccounts aan dat het SMTP-authenticatieprotocol in de afgelopen 7 dagen heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ffbec-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![De widget SMTP-auth-clients in het dashboard voor de e-mail stroom van het beveiligings & nalevings centrum](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="ffbec-110">Als u op het aantal berichten in het object klikt, wordt een flyout **SMTP auth clients** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffbec-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="ffbec-111">Het flyout biedt een geaggregeerde weergave van het TLS-gebruik en de volumes voor de laatste week.</span><span class="sxs-lookup"><span data-stu-id="ffbec-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Info-flyout na klikken op de widget SMTP-auth-clients in het dashboard voor e-mail stroom](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="ffbec-113">U kunt op de koppeling naar de **SMTP-auth-clients** klikken om naar de lijst met SMTP-verificatie clients te gaan, zoals wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="ffbec-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="ffbec-114">SMTP-verificatierapport voor clients</span><span class="sxs-lookup"><span data-stu-id="ffbec-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="ffbec-115">Rapportweergave voor het rapport met SMTP-verificatie clients</span><span class="sxs-lookup"><span data-stu-id="ffbec-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="ffbec-116">In het rapport worden standaardgegevens weergegeven voor de laatste 7 dagen, maar de gegevens zijn beschikbaar voor de laatste 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="ffbec-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="ffbec-117">De sectie overzicht bevat de volgende grafieken:</span><span class="sxs-lookup"><span data-stu-id="ffbec-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="ffbec-118">**Gegevens weergeven voor: verzenden volume**: in de grafiek worden standaard de SMTP-auth-client berichten weergegeven die zijn verzonden vanuit alle domeinen (**gegevens weergeven voor: alle domeinen** van de afzender worden standaard geselecteerd).</span><span class="sxs-lookup"><span data-stu-id="ffbec-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="ffbec-119">U kunt de resultaten filteren op een bepaald domein van de afzender door op **gegevens weergeven voor** te klikken en het domein van de afzender in de vervolgkeuzelijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ffbec-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="ffbec-120">Als u een specifiek gegevenspunt (dag) aanwijst, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffbec-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![De weergave volume in het rapport SMTP-auth-clients verzenden in het Beveiligingscentrum voor beveiliging &](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="ffbec-122">**Gegevens weergeven op: TLS**: de grafiek bevat het percentage van TLS-gebruik voor alle SMTP auth-client berichten tijdens de geselecteerde tijdsperiode.</span><span class="sxs-lookup"><span data-stu-id="ffbec-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="ffbec-123">Met deze grafiek kunt u de gebruikers en systeemaccounts identificeren en er actie ondernemen wanneer u nog oudere versies van TLS gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ffbec-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Voorbeeld van TLS-weergave in het rapport SMTP-auth-clients in het nalevings centrum voor beveiligings &](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="ffbec-125">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="ffbec-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ffbec-126">Klik op **rapportaanvragen** om een gedetailleerde versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ffbec-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="ffbec-127">U kunt het datumbereik en de geadresseerden opgeven waarop u het rapport wilt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ffbec-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="ffbec-128">Weergave Details voor het rapport met SMTP-verificatie clients</span><span class="sxs-lookup"><span data-stu-id="ffbec-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="ffbec-129">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="ffbec-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ffbec-130">**Gegevens weergeven voor: verzenden volume**: de volgende informatie wordt weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="ffbec-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="ffbec-131">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="ffbec-131">**Sender address**</span></span>
  - <span data-ttu-id="ffbec-132">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="ffbec-132">**Message count**</span></span>

  <span data-ttu-id="ffbec-133">Als u een rij selecteert, worden de gegevens in een flyout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffbec-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="ffbec-134">**Gegevens weergeven op: TLS-gebruik**: de volgende informatie wordt weergegeven in een tabel:</span><span class="sxs-lookup"><span data-stu-id="ffbec-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="ffbec-135">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="ffbec-135">**Sender address**</span></span>
  - <span data-ttu-id="ffbec-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffbec-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="ffbec-137">**TLS 1,1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffbec-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="ffbec-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffbec-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="ffbec-139">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="ffbec-139">**Message count**</span></span>

  <span data-ttu-id="ffbec-140"><sup>\*</sup> In deze kolom ziet u het percentage en het aantal berichten van de afzender.</span><span class="sxs-lookup"><span data-stu-id="ffbec-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="ffbec-141">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="ffbec-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ffbec-142">Als u een rij selecteert, worden dezelfde gegevens weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="ffbec-142">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details van de lijst Details van de weergave TLS-verificatie clients](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="ffbec-144">Klik op **rapportaanvragen** om een gedetailleerde versie van het rapport in een e-mailbericht te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ffbec-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="ffbec-145">U kunt het datumbereik en de geadresseerden opgeven waarop u het rapport wilt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ffbec-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="ffbec-146">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="ffbec-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ffbec-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ffbec-147">Related topics</span></span>

<span data-ttu-id="ffbec-148">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="ffbec-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
