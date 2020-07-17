---
title: Berichten in quarantaine zoeken en vrijgeven als gebruiker
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
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
ms.openlocfilehash: 01125b7aa0a89c27cdc8abc5ebb46da4b11ac504
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936981"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="7142f-103">Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP</span><span class="sxs-lookup"><span data-stu-id="7142f-103">Find and release quarantined messages as a user in EOP</span></span>

<span data-ttu-id="7142f-104">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="7142f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="7142f-105">Zie [Quarantaine in EOP](quarantine-email-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7142f-105">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="7142f-106">Als gebruiker kunt u uw berichten in quarantaine zien, vrijgeven en verwijderen, als u een ontvanger bent en het bericht in quarantaine is geplaatst als spam of bulkmail.</span><span class="sxs-lookup"><span data-stu-id="7142f-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="7142f-107">Vanaf april 2020 kunt u phishingberichten (niet de e-mails met hoge waarschijnlijkheid) weergeven of verwijderen als u een ontvanger bent.</span><span class="sxs-lookup"><span data-stu-id="7142f-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="7142f-108">U kunt uw in quarantaine geplaatste berichten weergeven en beheren in het beveiligings- en compliancecentrum of (als een beheerder dit heeft ingesteld) in [spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7142f-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7142f-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="7142f-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7142f-110">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="7142f-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="7142f-111">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="7142f-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="7142f-112">Beheerders kunnen instellen hoe lang berichten in quarantaine blijven voordat ze permanent worden verwijderd (antispambeleid).</span><span class="sxs-lookup"><span data-stu-id="7142f-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="7142f-113">Berichten waarvan de quarantaine is verlopen, kunnen niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="7142f-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="7142f-114">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7142f-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="7142f-115">Beheerders kunnen ook [Spammeldingen voor eindgebruikers inschakelen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="7142f-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="7142f-116">Gebruikers kunnen ongewenste, in quarantaine geplaatste berichten vrijgeven, maar in quarantaine geplaatste berichten niet rechtstreeks uit deze meldingen halen.</span><span class="sxs-lookup"><span data-stu-id="7142f-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="7142f-117">Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7142f-117">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="7142f-118">Berichten die in quarantaine zijn geplaatst voor phishing van vertrouwelijke informatie, malware of door e-mailstroomregels (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="7142f-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="7142f-119">Phishingberichten kunnen door gebruikers worden bekeken en vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="7142f-119">Phish messages can be reviewed and released by users.</span></span> <span data-ttu-id="7142f-120">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="7142f-120">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="7142f-121">U kunt een bericht slechts eenmaal vrijgeven en melden als fout-positief (geen ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="7142f-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="7142f-122">Uw berichten in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="7142f-122">View your quarantined messages</span></span>

1. <span data-ttu-id="7142f-123">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="7142f-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="7142f-124">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="7142f-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="7142f-125">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="7142f-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="7142f-126">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="7142f-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="7142f-127">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-128">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-129">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-130">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-131">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-132">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-133">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7142f-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="7142f-134">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="7142f-134">**Recipient**</span></span>

   - <span data-ttu-id="7142f-135">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="7142f-135">**Message ID**</span></span>

   - <span data-ttu-id="7142f-136">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="7142f-136">**Policy name**</span></span>

   - <span data-ttu-id="7142f-137">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="7142f-137">**Size**</span></span>

   - <span data-ttu-id="7142f-138">**Richting**</span><span class="sxs-lookup"><span data-stu-id="7142f-138">**Direction**</span></span>

   <span data-ttu-id="7142f-139">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7142f-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="7142f-140">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="7142f-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="7142f-141">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="7142f-141">The available filters are:</span></span>

   - <span data-ttu-id="7142f-142">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="7142f-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="7142f-143">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="7142f-143">**Today**</span></span>

     - <span data-ttu-id="7142f-144">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="7142f-144">**Next 2 days**</span></span>

     - <span data-ttu-id="7142f-145">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="7142f-145">**Next 7 days**</span></span>

     - <span data-ttu-id="7142f-146">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="7142f-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="7142f-147">**Ontvangen op**: voer een **begindatum** en**einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="7142f-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="7142f-148">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="7142f-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="7142f-149">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="7142f-149">**Bulk**</span></span>

     - <span data-ttu-id="7142f-150">**Spam**</span><span class="sxs-lookup"><span data-stu-id="7142f-150">**Spam**</span></span>

     - <span data-ttu-id="7142f-151">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="7142f-151">**Phish**</span></span>

   <span data-ttu-id="7142f-152">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="7142f-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="7142f-153">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="7142f-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="7142f-154">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="7142f-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="7142f-155">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7142f-155">Wildcards aren't supported.</span></span> <span data-ttu-id="7142f-156">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="7142f-156">You can search by the following values:</span></span>

   - <span data-ttu-id="7142f-157">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="7142f-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="7142f-158">Als u een bericht selecteert in de lijst, verschijnt de waarde **Bericht-ID** in het deelvenster **Details** dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7142f-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="7142f-159">Beheerders kunnen [berichttracering](message-trace-scc.md) gebruiken om naar berichten en de bijbehorende bericht-ID’s te zoeken.</span><span class="sxs-lookup"><span data-stu-id="7142f-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="7142f-160">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="7142f-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="7142f-161">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="7142f-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="7142f-162">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="7142f-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="7142f-163">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="7142f-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="7142f-164">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="7142f-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="7142f-165">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="7142f-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="7142f-166">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="7142f-166">Export message results</span></span>

1. <span data-ttu-id="7142f-167">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="7142f-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="7142f-168">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="7142f-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="7142f-169">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="7142f-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="7142f-170">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="7142f-170">View quarantined message details</span></span>

<span data-ttu-id="7142f-171">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="7142f-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="7142f-172">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="7142f-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="7142f-173">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="7142f-173">**Sender address**</span></span>

- <span data-ttu-id="7142f-174">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="7142f-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="7142f-175">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="7142f-175">**Subject**</span></span>

- <span data-ttu-id="7142f-176">**Reden van quarantaine**: wordt getoond als een bericht is geïdentificeerd als **Spam**, **Bulk** of **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="7142f-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="7142f-177">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="7142f-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="7142f-178">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="7142f-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="7142f-179">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="7142f-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="7142f-180">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="7142f-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="7142f-181">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="7142f-181">Take action on quarantined email</span></span>

<span data-ttu-id="7142f-182">Nadat u een bericht selecteert, krijgt u in het deelvenster **Details** opties wat u met het bericht kunt doen:</span><span class="sxs-lookup"><span data-stu-id="7142f-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="7142f-183">**Bericht vrijgeven**: kies in het deelvenster dat wordt weergegeven of u **Berichten wilt rapporteren aan Microsoft voor analyse**.</span><span class="sxs-lookup"><span data-stu-id="7142f-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="7142f-184">Dit is standaard geselecteerd en rapporteert het bericht dat onterecht in quarantaine is geplaatst aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="7142f-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="7142f-185">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7142f-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="7142f-186">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="7142f-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="7142f-187">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="7142f-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="7142f-188">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="7142f-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="7142f-189">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="7142f-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="7142f-190">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="7142f-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="7142f-191">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="7142f-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="7142f-192">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="7142f-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="7142f-193">**Verwijderen uit quarantaine**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="7142f-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="7142f-194">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7142f-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="7142f-195">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="7142f-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="7142f-196">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="7142f-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="7142f-197">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="7142f-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="7142f-198">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="7142f-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="7142f-199">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="7142f-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="7142f-200">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7142f-200">When you're finished, click **Close**.</span></span>
