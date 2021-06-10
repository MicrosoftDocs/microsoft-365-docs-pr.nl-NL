---
title: Inzicht in nieuwe gebruikers die e-mails doorsturen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen leren hoe ze het inzicht van nieuwe gebruikers voor het doorsturen van e-mail in het beveiligings- & compliancecentrum kunnen gebruiken om te onderzoeken wanneer gebruikers in hun organisatie berichten doorsturen naar nieuwe domeinen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204489"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="7e845-103">Nieuwe gebruikers die inzicht in e-mail doorsturen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="7e845-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7e845-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="7e845-104">**Applies to**</span></span>
- [<span data-ttu-id="7e845-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7e845-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7e845-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="7e845-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7e845-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e845-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7e845-108">Het is verdacht wanneer nieuwe gebruikersaccounts in uw organisatie plotseling e-mailberichten doorsturen naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="7e845-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="7e845-109">De **nieuwe domeinen die** e-mailinzicht worden doorgestuurd in het beveiligings- & [compliancecentrum,](https://protection.office.com) worden u op de hoogte gehouden wanneer nieuwe gebruikers in uw organisatie berichten doorsturen naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="7e845-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="7e845-110">Deze voorwaarde kan aangeven dat gecompromitteerde beheerdersaccounts zijn gebruikt om de nieuwe gebruikers te maken.</span><span class="sxs-lookup"><span data-stu-id="7e845-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="7e845-111">Zie Reageren op een gekromd [e-mailaccount](responding-to-a-compromised-email-account.md)als u vermoedt dat de accounts zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="7e845-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="7e845-112">Dit inzicht wordt alleen weergegeven wanneer het probleem wordt gedetecteerd en wordt weergegeven op de pagina [Rapport](view-mail-flow-reports.md#forwarding-report) doorsturen.</span><span class="sxs-lookup"><span data-stu-id="7e845-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe gebruikers die e-mails doorsturen](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="7e845-114">Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer [](#forwarding-modifications-report) informatie over de doorgestuurde berichten kunt vinden, waaronder een koppeling naar het rapport Wijzigingen doorsturen, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="7e845-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Details flyout die wordt weergegeven nadat u hebt geklikt op het inzicht van nieuwe gebruikers voor het doorsturen van e-mail](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="7e845-116">U kunt ook naar deze detailspagina gaan wanneer u het inzicht selecteert nadat u op Alles weergeven hebt geklikt **in** het gebied Top **insights & aanbevelingen** op ( \> **Rapportendashboard** of <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="7e845-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="7e845-117">U kunt op de **koppeling Rapport zien dat is** gekoppeld aan inzicht klikken om naar het rapport Wijzigingen doorsturen te gaan, zoals beschreven in de volgende sectie. </span><span class="sxs-lookup"><span data-stu-id="7e845-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="7e845-118">Rapport Wijzigingen doorsturen</span><span class="sxs-lookup"><span data-stu-id="7e845-118">Forwarding modifications report</span></span>

<span data-ttu-id="7e845-119">Het **rapport Wijzigingen doorsturen bevat** details over berichten die automatisch worden doorgestuurd van afzenders in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="7e845-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="7e845-120">Nieuw gemaakte accounts die berichten doorsturen naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="7e845-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="7e845-121">Accounts die berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd naar andere afzenders in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e845-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="7e845-122">Deze typen doorgestuurde berichten kunnen een beveiligings- of compliancerisico opleveren, en kunnen gecompromitteerde accounts aangeven.</span><span class="sxs-lookup"><span data-stu-id="7e845-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="7e845-123">Het rapport bevat gegevens voor maximaal 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="7e845-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="7e845-124">Standaard worden in het rapport gegevens van de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7e845-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="7e845-125">Dit rapport is niet rechtstreeks beschikbaar in het [e-mailstroomdashboard](mail-flow-insights-v2.md) of in het [dashboard Rapporten.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="7e845-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="7e845-126">Naast het klikken op de koppeling Rapport  bekijken **die is** gekoppeld aan de koppeling Inzicht in het inzicht van nieuwe gebruikers voor het doorsturen van e-mail, gaat u naar het rapport door:</span><span class="sxs-lookup"><span data-stu-id="7e845-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="7e845-127">Klik op de **koppeling Meldingen doorsturen** in de details van de nieuwe domeinen die per e-mail [worden doorgestuurd.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="7e845-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="7e845-128">Openen <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="7e845-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="7e845-129">Rapportweergave voor het rapport Wijzigingen doorsturen</span><span class="sxs-lookup"><span data-stu-id="7e845-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="7e845-130">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="7e845-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="7e845-131">**Gegevens voor: Nieuwe doorsturende gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="7e845-131">**Show data for: New forwarding users**:</span></span>

  ![Weergave Nieuwe doorsturende gebruikers in het rapport Wijzigingen doorsturen](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="7e845-133">**Gegevens voor: Nieuwe doorsturende domeinen:**</span><span class="sxs-lookup"><span data-stu-id="7e845-133">**Show data for: New forwarding domains**:</span></span>

  ![Weergave Nieuwe doorgestuurde domeinen in het rapport Wijzigingen doorsturen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="7e845-135">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="7e845-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="7e845-136">Tabelweergave details voor het rapport Wijzigingen doorsturen</span><span class="sxs-lookup"><span data-stu-id="7e845-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="7e845-137">Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:</span><span class="sxs-lookup"><span data-stu-id="7e845-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7e845-138">**Gegevens voor: Nieuwe doorsturende gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="7e845-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="7e845-139">**Naam:** Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="7e845-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="7e845-140">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="7e845-140">**Forwarding type**</span></span>
  - <span data-ttu-id="7e845-141">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="7e845-141">**Recipient address**</span></span>
  - <span data-ttu-id="7e845-142">**Details**</span><span class="sxs-lookup"><span data-stu-id="7e845-142">**Details**</span></span>
  - <span data-ttu-id="7e845-143">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="7e845-143">**Count**</span></span>
  - <span data-ttu-id="7e845-144">**Eerste doorgestuurde datum**</span><span class="sxs-lookup"><span data-stu-id="7e845-144">**First forward date**</span></span>

- <span data-ttu-id="7e845-145">**Gegevens voor: Nieuwe doorsturende domeinen:**</span><span class="sxs-lookup"><span data-stu-id="7e845-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="7e845-146">**Naam:** Het e-maildomein van de afzender.</span><span class="sxs-lookup"><span data-stu-id="7e845-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="7e845-147">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="7e845-147">**Forwarding type**</span></span>
  - <span data-ttu-id="7e845-148">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="7e845-148">**Recipient address**</span></span>
  - <span data-ttu-id="7e845-149">**Details**</span><span class="sxs-lookup"><span data-stu-id="7e845-149">**Details**</span></span>
  - <span data-ttu-id="7e845-150">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="7e845-150">**Count**</span></span>
  - <span data-ttu-id="7e845-151">**Eerste doorgestuurde datum**</span><span class="sxs-lookup"><span data-stu-id="7e845-151">**First forward date**</span></span>

<span data-ttu-id="7e845-152">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="7e845-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="7e845-153">Als u een rij in de tabel selecteert, wordt een fly-out **Details** weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="7e845-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="7e845-154">**Naam:** Dit is het e-mailadres van de afzender (van Gegevens weergeven **voor:** weergave Nieuwe doorsturende gebruikers) of het e-maildomein van de afzender (van Gegevens weergeven **voor:** Weergave Nieuwe doorsturende domeinen).</span><span class="sxs-lookup"><span data-stu-id="7e845-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="7e845-155">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="7e845-155">**Forwarding type**</span></span>
- <span data-ttu-id="7e845-156">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="7e845-156">**Recipient**</span></span>
- <span data-ttu-id="7e845-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="7e845-157">**Details**</span></span>
- <span data-ttu-id="7e845-158">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="7e845-158">**Count**</span></span>
- <span data-ttu-id="7e845-159">**Begindatum**</span><span class="sxs-lookup"><span data-stu-id="7e845-159">**Start date**</span></span>
- <span data-ttu-id="7e845-160">**Aanbeveling:** Vanaf hier kunt u op de koppeling klikken om de gebruiker te beheren in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="7e845-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Details flyout from the details table of the New forwarding users view in the Forwarding modifications report](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="7e845-162">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="7e845-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e845-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e845-163">Related topics</span></span>

<span data-ttu-id="7e845-164">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="7e845-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
