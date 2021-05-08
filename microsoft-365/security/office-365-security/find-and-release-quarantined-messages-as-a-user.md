---
title: Berichten in quarantaine zoeken en vrijgeven als gebruiker
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gebruikers kunnen meer informatie krijgen over het weergeven en beheren van berichten in quarantaine in Exchange Online Protection (EOP) die aan hun hadden moeten worden afgeleverd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 036aa164b8b77efd2365d56c07d26870eac243f5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274446"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="0abf6-103">Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP</span><span class="sxs-lookup"><span data-stu-id="0abf6-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0abf6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0abf6-104">**Applies to**</span></span>
- [<span data-ttu-id="0abf6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0abf6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0abf6-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0abf6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0abf6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0abf6-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0abf6-108">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="0abf6-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="0abf6-109">Zie [Quarantaine in EOP](quarantine-email-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0abf6-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="0abf6-110">Als gebruiker kunt u uw berichten in quarantaine zien, vrijgeven en verwijderen, als u een ontvanger bent en het bericht in quarantaine is geplaatst als spam of bulkmail.</span><span class="sxs-lookup"><span data-stu-id="0abf6-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="0abf6-111">Vanaf april 2020 kunt u phishingberichten (niet de e-mails met hoge waarschijnlijkheid) weergeven of verwijderen als u een ontvanger bent.</span><span class="sxs-lookup"><span data-stu-id="0abf6-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="0abf6-112">U kunt uw in quarantaine geplaatste berichten weergeven en beheren in het beveiligings- en compliancecentrum of (als een beheerder dit heeft ingesteld) in [spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0abf6-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0abf6-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="0abf6-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0abf6-114">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="0abf6-115">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="0abf6-116">Beheerders kunnen instellen hoe lang berichten in quarantaine blijven voordat ze permanent worden verwijderd (antispambeleid).</span><span class="sxs-lookup"><span data-stu-id="0abf6-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="0abf6-117">Berichten waarvan de quarantaine is verlopen, kunnen niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="0abf6-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="0abf6-118">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0abf6-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="0abf6-119">Beheerders kunnen ook [Spammeldingen voor eindgebruikers inschakelen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="0abf6-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="0abf6-120">Gebruikers kunnen in quarantaine geplaatste ongewenste berichten rechtstreeks vanuit deze meldingen vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="0abf6-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="0abf6-121">Gebruikers kunnen in quarantaine geplaatste phishingberichten (niet phishingberichten van hoge waarschijnlijkheid) rechtstreeks vanuit deze meldingen controleren.</span><span class="sxs-lookup"><span data-stu-id="0abf6-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="0abf6-122">Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0abf6-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="0abf6-123">Berichten die in quarantaine zijn geplaatst voor phishing van hoge waarschijnlijkheid, malware of door e-mailstroomregels (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders en zijn niet zichtbaar voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0abf6-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="0abf6-124">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0abf6-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="0abf6-125">U kunt een bericht slechts eenmaal vrijgeven en melden als fout-positief (geen ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="0abf6-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="0abf6-126">Uw berichten in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="0abf6-126">View your quarantined messages</span></span>

1. <span data-ttu-id="0abf6-127">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="0abf6-128">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="0abf6-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="0abf6-129">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="0abf6-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="0abf6-130">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="0abf6-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="0abf6-131">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-132">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-133">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-134">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-135">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-136">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-137">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0abf6-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="0abf6-138">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="0abf6-138">**Recipient**</span></span>
   - <span data-ttu-id="0abf6-139">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="0abf6-139">**Message ID**</span></span>
   - <span data-ttu-id="0abf6-140">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="0abf6-140">**Policy name**</span></span>
   - <span data-ttu-id="0abf6-141">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="0abf6-141">**Size**</span></span>
   - <span data-ttu-id="0abf6-142">**Richting**</span><span class="sxs-lookup"><span data-stu-id="0abf6-142">**Direction**</span></span>

   <span data-ttu-id="0abf6-143">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0abf6-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="0abf6-144">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="0abf6-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="0abf6-145">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="0abf6-145">The available filters are:</span></span>

   - <span data-ttu-id="0abf6-146">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="0abf6-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="0abf6-147">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="0abf6-147">**Today**</span></span>
     - <span data-ttu-id="0abf6-148">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="0abf6-148">**Next 2 days**</span></span>
     - <span data-ttu-id="0abf6-149">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="0abf6-149">**Next 7 days**</span></span>
     - <span data-ttu-id="0abf6-150">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="0abf6-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0abf6-151">**Ontvangen op**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="0abf6-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0abf6-152">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="0abf6-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="0abf6-153">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="0abf6-153">**Bulk**</span></span>
     - <span data-ttu-id="0abf6-154">**Spam**</span><span class="sxs-lookup"><span data-stu-id="0abf6-154">**Spam**</span></span>
     - <span data-ttu-id="0abf6-155">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="0abf6-155">**Phish**</span></span>

   - <span data-ttu-id="0abf6-156">**Beleidstype**: berichten filteren op beleidstype:</span><span class="sxs-lookup"><span data-stu-id="0abf6-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="0abf6-157">**Beleid tegen phishing**</span><span class="sxs-lookup"><span data-stu-id="0abf6-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="0abf6-158">**Beleid voor gehoste inhoudsfilters** (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="0abf6-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="0abf6-159">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="0abf6-160">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="0abf6-161">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="0abf6-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="0abf6-162">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="0abf6-162">Wildcards aren't supported.</span></span> <span data-ttu-id="0abf6-163">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="0abf6-163">You can search by the following values:</span></span>

   - <span data-ttu-id="0abf6-164">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0abf6-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="0abf6-165">Als u een bericht selecteert in de lijst, verschijnt de waarde **Bericht-ID** in het deelvenster **Details** dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0abf6-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="0abf6-166">Beheerders kunnen [berichttracering](message-trace-scc.md) gebruiken om naar berichten en de bijbehorende bericht-ID’s te zoeken.</span><span class="sxs-lookup"><span data-stu-id="0abf6-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="0abf6-167">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="0abf6-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="0abf6-168">**Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0abf6-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="0abf6-169">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="0abf6-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="0abf6-170">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="0abf6-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="0abf6-171">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0abf6-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="0abf6-172">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="0abf6-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="0abf6-173">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="0abf6-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="0abf6-174">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="0abf6-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="0abf6-175">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="0abf6-175">Export message results</span></span>

1. <span data-ttu-id="0abf6-176">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="0abf6-177">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="0abf6-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="0abf6-178">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="0abf6-179">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="0abf6-179">View quarantined message details</span></span>

<span data-ttu-id="0abf6-180">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="0abf6-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0abf6-181">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0abf6-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="0abf6-182">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="0abf6-182">**Sender address**</span></span>

- <span data-ttu-id="0abf6-183">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="0abf6-184">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="0abf6-184">**Subject**</span></span>

- <span data-ttu-id="0abf6-185">**Reden van quarantaine**: wordt getoond als een bericht is geïdentificeerd als **Spam**, **Bulk** of **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="0abf6-186">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="0abf6-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="0abf6-187">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="0abf6-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="0abf6-188">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="0abf6-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="0abf6-189">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="0abf6-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="0abf6-190">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0abf6-190">Take action on quarantined email</span></span>

<span data-ttu-id="0abf6-191">Nadat u een bericht selecteert, krijgt u in het deelvenster **Details** opties wat u met het bericht kunt doen:</span><span class="sxs-lookup"><span data-stu-id="0abf6-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0abf6-192">**Bericht vrijgeven**: kies in het deelvenster dat wordt weergegeven of u **Berichten wilt rapporteren aan Microsoft voor analyse**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="0abf6-193">Dit is standaard geselecteerd en rapporteert het bericht dat onterecht in quarantaine is geplaatst aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="0abf6-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="0abf6-194">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0abf6-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="0abf6-195">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0abf6-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="0abf6-196">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="0abf6-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="0abf6-197">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="0abf6-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="0abf6-198">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="0abf6-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="0abf6-199">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="0abf6-200">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="0abf6-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="0abf6-201">**Verwijderen uit quarantaine**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0abf6-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="0abf6-202">**Afzenders blokkeren**: voeg de afzender toe aan de lijst met geblokkeerde afzenders in uw postvak.</span><span class="sxs-lookup"><span data-stu-id="0abf6-202">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="0abf6-203">Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0abf6-203">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="0abf6-204">Voeg de afzender toe aan de lijst met geblokkeerde afzenders in uw postvak.</span><span class="sxs-lookup"><span data-stu-id="0abf6-204">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="0abf6-205">Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0abf6-205">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="0abf6-206">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0abf6-206">When you're finished, click **Close**.</span></span>

<span data-ttu-id="0abf6-207">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="0abf6-207">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="0abf6-208">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="0abf6-208">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="0abf6-209">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0abf6-209">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="0abf6-210">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="0abf6-210">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="0abf6-211">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="0abf6-211">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="0abf6-212">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="0abf6-212">When you're finished, click **Close**.</span></span>
