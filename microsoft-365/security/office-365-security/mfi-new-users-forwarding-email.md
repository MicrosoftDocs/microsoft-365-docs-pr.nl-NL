---
title: Inzicht in nieuwe gebruikers die e-mails doorsturen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen informatie over het gebruik van de nieuwe gebruikers die e-mail inzicht doorsturen in het beveiligings & Conformiteitscentrum gebruiken om te onderzoeken wanneer gebruikers in hun organisatie berichten doorsturen naar nieuwe domeinen.
ms.openlocfilehash: 42f8c536f8a8a1421d97726c7af432c01d053b05
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200653"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="564db-103">Nieuwe gebruikers die e-mail inzicht doorsturen in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="564db-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="564db-104">Het verdacht wanneer nieuwe gebruikersaccounts in uw organisatie zich plotseling voor het doorsturen van e-mailberichten naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="564db-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="564db-105">De **nieuwe domeinen waarnaar e-mail inzicht wordt doorgestuurd** in de [beveiliging & nalevings centrum](https://protection.office.com) meldt dat u een melding krijgt wanneer nieuwe gebruikers in uw organisatie berichten doorsturen naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="564db-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="564db-106">Deze voorwaarde kan worden gebruikt voor het maken van beheerdersaccounts waarmee de nieuwe gebruikers zijn gemanipuleerd.</span><span class="sxs-lookup"><span data-stu-id="564db-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="564db-107">Als u vermoedt dat de accounts zijn aangetast, raadpleegt u [reageren op een gemanipuleerd e-mailaccount](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span><span class="sxs-lookup"><span data-stu-id="564db-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="564db-108">Dit inzicht wordt alleen weergegeven als het probleem zich voordoet, en wordt weergegeven op de pagina voor het [doorsturen van rapporten](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="564db-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe gebruikers die e-mails doorsturen](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="564db-110">Wanneer u op de widget klikt, verschijnt er een flyout waar u meer informatie kunt vinden over de doorgestuurde berichten, waaronder een koppeling naar het [rapport met doorsturen van wijzigingen](#forwarding-modifications-report) , zoals verderop in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="564db-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![Info-menu dat wordt weergegeven nadat u hebt geklikt op de nieuwe gebruikers e-mail doorsturen](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="564db-112">U kunt deze detailpagina ook raadplegen wanneer u het inzicht selecteert nadat u op **AllesWeergeven** hebt geklikt in het gebied **belangrijkste inzichten &** gebied voor aanbevelingen (**Reports** \> **Dashboard** rapporten of <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="564db-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="564db-113">U kunt klikken op de koppeling **Zie het rapport dat is gekoppeld** aan de Insight-koppeling om naar het **rapport met doorstuur wijzigingen** te gaan, zoals in de volgende sectie is beschreven.</span><span class="sxs-lookup"><span data-stu-id="564db-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="564db-114">Rapport over wijzigingen doorsturen</span><span class="sxs-lookup"><span data-stu-id="564db-114">Forwarding modifications report</span></span>

<span data-ttu-id="564db-115">In het rapport met de **doorstuur wijzigingen** ziet u informatie over berichten die automatisch worden doorgestuurd van afzenders in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="564db-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="564db-116">Zojuist gemaakte accounts die berichten doorsturen naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="564db-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="564db-117">Accounts die berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd naar andere afzenders in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="564db-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="564db-118">Dit soort doorgestuurde berichten kan een beveiligings-of nalevings risico vormen, en kan worden aangeduid met gemanipuleerde accounts.</span><span class="sxs-lookup"><span data-stu-id="564db-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="564db-119">Het rapport bevat gegevens voor maximaal 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="564db-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="564db-120">In het rapport worden standaardgegevens weergegeven voor de laatste 7 dagen.</span><span class="sxs-lookup"><span data-stu-id="564db-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="564db-121">Dit rapport is niet rechtstreeks beschikbaar in het dash [Board voor e-mail stroom](mail-flow-insights-v2.md) of in het [Dashboard rapporten](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="564db-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="564db-122">U krijgt niet alleen te klikken op de koppeling **Zie het rapport in verband met een inzicht** in de **nieuwe gebruikers die e-mail inzicht doorsturen** :</span><span class="sxs-lookup"><span data-stu-id="564db-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="564db-123">Op de koppeling **meldingen doorsturen** klikken in de details van de [nieuwe domeinen die worden doorgestuurd naar e-mail](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="564db-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="564db-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="564db-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="564db-125">Rapportweergave voor het rapport voor het doorsturen van wijzigingen</span><span class="sxs-lookup"><span data-stu-id="564db-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="564db-126">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="564db-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="564db-127">**Gegevens weergeven voor: nieuwe doorstuur gebruikers**:</span><span class="sxs-lookup"><span data-stu-id="564db-127">**Show data for: New forwarding users**:</span></span>

  ![Nieuwe weergave voor het doorsturen van gebruikers in het rapport met doorgestuurde wijzigingen](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="564db-129">**Gegevens weergeven voor: nieuwe forwarding domains**:</span><span class="sxs-lookup"><span data-stu-id="564db-129">**Show data for: New forwarding domains**:</span></span>

  ![Nieuwe weergave van doorgestuurd domein in het rapport voor het doorsturen van wijzigingen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="564db-131">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="564db-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="564db-132">De tabel weergave Details voor het rapport met wijzigingen doorsturen</span><span class="sxs-lookup"><span data-stu-id="564db-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="564db-133">Als u op **detail tabel weergeven**klikt, is de informatie die wordt weergegeven, afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="564db-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="564db-134">**Gegevens weergeven voor: nieuwe doorstuur gebruikers**:</span><span class="sxs-lookup"><span data-stu-id="564db-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="564db-135">**Naam**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="564db-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="564db-136">**Type forwarding**</span><span class="sxs-lookup"><span data-stu-id="564db-136">**Forwarding type**</span></span>
  - <span data-ttu-id="564db-137">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="564db-137">**Recipient address**</span></span>
  - <span data-ttu-id="564db-138">**Details**</span><span class="sxs-lookup"><span data-stu-id="564db-138">**Details**</span></span>
  - <span data-ttu-id="564db-139">**Getal**</span><span class="sxs-lookup"><span data-stu-id="564db-139">**Count**</span></span>
  - <span data-ttu-id="564db-140">**Eerste doorstuur datum**</span><span class="sxs-lookup"><span data-stu-id="564db-140">**First forward date**</span></span>

- <span data-ttu-id="564db-141">**Gegevens weergeven voor: nieuwe forwarding domains**:</span><span class="sxs-lookup"><span data-stu-id="564db-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="564db-142">**Naam**: het e-mail domein van de afzender.</span><span class="sxs-lookup"><span data-stu-id="564db-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="564db-143">**Type forwarding**</span><span class="sxs-lookup"><span data-stu-id="564db-143">**Forwarding type**</span></span>
  - <span data-ttu-id="564db-144">**Adres van ontvanger**</span><span class="sxs-lookup"><span data-stu-id="564db-144">**Recipient address**</span></span>
  - <span data-ttu-id="564db-145">**Details**</span><span class="sxs-lookup"><span data-stu-id="564db-145">**Details**</span></span>
  - <span data-ttu-id="564db-146">**Getal**</span><span class="sxs-lookup"><span data-stu-id="564db-146">**Count**</span></span>
  - <span data-ttu-id="564db-147">**Eerste doorstuur datum**</span><span class="sxs-lookup"><span data-stu-id="564db-147">**First forward date**</span></span>

<span data-ttu-id="564db-148">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="564db-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="564db-149">Als u een rij in de tabel selecteert, wordt een flyout met **Details** weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="564db-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="564db-150">**Naam**: dit is het e-mailadres van de afzender (van **gegevens weergeven voor: nieuwe weergave voor doorstuur gebruikers** ) of het e-mail domein van de afzender (van **gegevens weergeven voor: nieuwe weergave met forwarding domains** ).</span><span class="sxs-lookup"><span data-stu-id="564db-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="564db-151">**Type forwarding**</span><span class="sxs-lookup"><span data-stu-id="564db-151">**Forwarding type**</span></span>
- <span data-ttu-id="564db-152">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="564db-152">**Recipient**</span></span>
- <span data-ttu-id="564db-153">**Details**</span><span class="sxs-lookup"><span data-stu-id="564db-153">**Details**</span></span>
- <span data-ttu-id="564db-154">**Getal**</span><span class="sxs-lookup"><span data-stu-id="564db-154">**Count**</span></span>
- <span data-ttu-id="564db-155">**Begindatum**</span><span class="sxs-lookup"><span data-stu-id="564db-155">**Start date**</span></span>
- <span data-ttu-id="564db-156">**Aanbeveling**: van hieruit kunt u klikken op de koppeling voor het beheren van de gebruiker in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="564db-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Flyout Details van de tabel Details van de nieuwe weergave voor het doorsturen van gebruikers in het rapport met doorgestuurde wijzigingen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="564db-158">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="564db-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="564db-159">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="564db-159">Related topics</span></span>

<span data-ttu-id="564db-160">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="564db-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
