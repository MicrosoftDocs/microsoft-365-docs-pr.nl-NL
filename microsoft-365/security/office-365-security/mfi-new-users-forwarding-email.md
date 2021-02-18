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
description: Beheerders kunnen in het beveiligings- &-compliancecentrum leren hoe ze het inzicht in e-mail doorsturen nieuwe gebruikers kunnen gebruiken om te onderzoeken wanneer gebruikers in hun organisatie berichten naar nieuwe domeinen doorsturen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9706951df480d07f4a6311e99cab5c9f404e999e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290819"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="ea551-103">Informatie over het doorsturen van e-mail door nieuwe gebruikers in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="ea551-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ea551-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ea551-104">**Applies to**</span></span>
- [<span data-ttu-id="ea551-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ea551-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ea551-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ea551-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ea551-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea551-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ea551-108">Het is verdacht als nieuwe gebruikersaccounts in uw organisatie plotseling beginnen met het doorsturen van e-mailberichten naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="ea551-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="ea551-109">De **nieuwe domeinen die** e-mailinzichten worden doorgestuurd in het [beveiligings- & Compliancecentrum](https://protection.office.com) melden u wanneer nieuwe gebruikers in uw organisatie berichten naar externe domeinen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="ea551-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="ea551-110">Deze voorwaarde kan aangeven dat gekromde beheerdersaccounts zijn gebruikt om de nieuwe gebruikers te maken.</span><span class="sxs-lookup"><span data-stu-id="ea551-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="ea551-111">Als u vermoedt dat de accounts zijn gehackt, bekijkt u Hoe u [reageert op een gekromd e-mailaccount.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="ea551-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="ea551-112">Dit inzicht wordt alleen weergegeven wanneer het probleem is gedetecteerd en wordt weergegeven op de [pagina Doorsturen-rapport.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="ea551-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe gebruikers die e-mails doorsturen](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="ea551-114">Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer [](#forwarding-modifications-report) informatie over de doorgestuurde berichten kunt vinden, waaronder een koppeling naar het rapport met doorgestuurde wijzigingen, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ea551-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Flyout details die wordt weergegeven nadat u op het inzicht van e-mail doorsturen van Nieuwe gebruikers hebt geklikt](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="ea551-116">U komt ook op deze detailpagina wanneer u het inzicht selecteert nadat u op Alles weergeven **hebt** geklikt in het gebied topinzichten **&** gebied voor aanbevelingen op (**Dashboard** Rapporten \>  of <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="ea551-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="ea551-117">U kunt klikken op de koppeling Rapport **bekijken dat** is gekoppeld aan de koppeling Inzichten om naar het rapport Doorsturen-wijzigingen **te** gaan, zoals wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="ea551-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="ea551-118">Rapport met doorgestuurde wijzigingen</span><span class="sxs-lookup"><span data-stu-id="ea551-118">Forwarding modifications report</span></span>

<span data-ttu-id="ea551-119">Het **rapport met doorgestuurde wijzigingen bevat** details over berichten die automatisch worden doorgestuurd van afzenders in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="ea551-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="ea551-120">Nieuw gemaakte accounts die berichten naar externe domeinen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="ea551-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="ea551-121">Accounts die berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd door andere afzenders in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ea551-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="ea551-122">Deze typen doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen, wat kan duiden op gekromde accounts.</span><span class="sxs-lookup"><span data-stu-id="ea551-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="ea551-123">Het rapport bevat gegevens voor maximaal 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="ea551-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="ea551-124">Standaard worden in het rapport gegevens van de afgelopen zeven dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ea551-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="ea551-125">Dit rapport is niet rechtstreeks beschikbaar in het [dashboard e-mailstroom](mail-flow-insights-v2.md) of in het [dashboard Rapporten.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="ea551-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="ea551-126">Naast het klikken op het rapport Bekijken  dat is gekoppeld aan **de koppeling** Inzicht in het inzicht van Nieuwe gebruikers voor het doorsturen van e-mail, gaat u naar het rapport door:</span><span class="sxs-lookup"><span data-stu-id="ea551-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="ea551-127">Klik op de **koppeling naar het rapport met doorgestuurde** meldingen in de details van de nieuwe domeinen die [e-mailinzicht worden doorgestuurd.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="ea551-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="ea551-128"><https://protection.office.com/reportv2?id=MailFlowNewForwarding>Openen.</span><span class="sxs-lookup"><span data-stu-id="ea551-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="ea551-129">Rapportweergave voor het rapport Met doorsturen</span><span class="sxs-lookup"><span data-stu-id="ea551-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="ea551-130">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="ea551-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ea551-131">**Gegevens tonen voor: Nieuwe doorsturende gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="ea551-131">**Show data for: New forwarding users**:</span></span>

  ![Weergave Nieuwe gebruikers voor doorsturen in het rapport Met doorsturen](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="ea551-133">**Gegevens tonen voor: nieuwe doorsturende domeinen:**</span><span class="sxs-lookup"><span data-stu-id="ea551-133">**Show data for: New forwarding domains**:</span></span>

  ![Weergave Nieuwe doorgestuurde domeinen in het rapport Met doorsturen](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="ea551-135">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="ea551-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="ea551-136">Detailtabelweergave voor het rapport Doorsturen van wijzigingen</span><span class="sxs-lookup"><span data-stu-id="ea551-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="ea551-137">Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:</span><span class="sxs-lookup"><span data-stu-id="ea551-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ea551-138">**Gegevens tonen voor: Nieuwe doorsturende gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="ea551-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="ea551-139">**Naam:** het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="ea551-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="ea551-140">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="ea551-140">**Forwarding type**</span></span>
  - <span data-ttu-id="ea551-141">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ea551-141">**Recipient address**</span></span>
  - <span data-ttu-id="ea551-142">**Details**</span><span class="sxs-lookup"><span data-stu-id="ea551-142">**Details**</span></span>
  - <span data-ttu-id="ea551-143">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="ea551-143">**Count**</span></span>
  - <span data-ttu-id="ea551-144">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="ea551-144">**First forward date**</span></span>

- <span data-ttu-id="ea551-145">**Gegevens tonen voor: nieuwe doorsturende domeinen:**</span><span class="sxs-lookup"><span data-stu-id="ea551-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="ea551-146">**Naam:** het e-maildomein van de afzender.</span><span class="sxs-lookup"><span data-stu-id="ea551-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="ea551-147">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="ea551-147">**Forwarding type**</span></span>
  - <span data-ttu-id="ea551-148">**Adres van geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="ea551-148">**Recipient address**</span></span>
  - <span data-ttu-id="ea551-149">**Details**</span><span class="sxs-lookup"><span data-stu-id="ea551-149">**Details**</span></span>
  - <span data-ttu-id="ea551-150">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="ea551-150">**Count**</span></span>
  - <span data-ttu-id="ea551-151">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="ea551-151">**First forward date**</span></span>

<span data-ttu-id="ea551-152">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="ea551-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ea551-153">Als u een rij in de tabel selecteert, wordt een flyout **Details** weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="ea551-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="ea551-154">**Naam:** dit is het e-mailadres van de afzender (van weergave Gegevens weergeven **voor:** Weergave Nieuwe doorgestuurde gebruikers) of het e-maildomein van de afzender (van de weergave Gegevens weergeven **voor:** Nieuwe doorsturende domeinen).</span><span class="sxs-lookup"><span data-stu-id="ea551-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="ea551-155">**Type doorsturen**</span><span class="sxs-lookup"><span data-stu-id="ea551-155">**Forwarding type**</span></span>
- <span data-ttu-id="ea551-156">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="ea551-156">**Recipient**</span></span>
- <span data-ttu-id="ea551-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="ea551-157">**Details**</span></span>
- <span data-ttu-id="ea551-158">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="ea551-158">**Count**</span></span>
- <span data-ttu-id="ea551-159">**Begindatum**</span><span class="sxs-lookup"><span data-stu-id="ea551-159">**Start date**</span></span>
- <span data-ttu-id="ea551-160">**Aanbeveling:** vanaf hier kunt u op de koppeling klikken om de gebruiker te beheren in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ea551-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Flyout Details uit de detailtabel van de weergave Nieuwe gebruikers voor doorsturen in het rapport Wijzigingen doorsturen](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="ea551-162">Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ea551-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea551-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ea551-163">Related topics</span></span>

<span data-ttu-id="ea551-164">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ea551-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
