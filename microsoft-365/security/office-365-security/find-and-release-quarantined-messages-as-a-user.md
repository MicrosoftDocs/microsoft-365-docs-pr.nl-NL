---
title: Berichten in quarantaine zoeken en vrijgeven als gebruiker in Office 365
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
description: Als Office 365-gebruiker kunt u uw berichten in quarantaine (berichten waarvan u ontvanger bent en het spamfilter het bericht in quarantaine heeft geplaatst als spam of bulkmail) zien, vrijgeven en verwijderen. U kunt uw berichten in quarantaine zien en beheren in het beveiligings- en compliancecentrum.
ms.openlocfilehash: 32ae03c555742b9f08c272806464ed75585d08df
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216902"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="1a4a0-104">Berichten in quarantaine zoeken en vrijgeven als gebruiker in Office 365</span><span class="sxs-lookup"><span data-stu-id="1a4a0-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="1a4a0-105">Potentieel gevaarlijke of ongewenste berichten worden in quarantaine geplaatst in Office 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="1a4a0-106">Zie [Quarantaine in Office 365](quarantine-email-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1a4a0-107">Als gebruiker kunt u uw berichten in quarantaine waarvan u ontvanger bent en het bericht in quarantaine werd geplaatst als spam, bulkmail of (vanaf april 2020) phishing, zien, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="1a4a0-108">U kunt uw in quarantaine geplaatste berichten weergeven en beheren in het beveiligings- en compliancecentrum of (als een beheerder dit heeft ingesteld) in [spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1a4a0-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="1a4a0-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1a4a0-110">Ga naar <https://protection.office.com> om het Office 365-beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-110">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="1a4a0-111">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="1a4a0-112">Beheerders kunnen instellen hoe lang berichten in quarantaine blijven voordat ze permanent worden verwijderd (antispambeleid).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="1a4a0-113">Berichten waarvan de quarantaine is verlopen, kunnen niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="1a4a0-114">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1a4a0-115">Beheerders kunnen ook [Spammeldingen voor eindgebruikers inschakelen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="1a4a0-116">Gebruikers kunnen ongewenste, in quarantaine geplaatste berichten vrijgeven, maar in quarantaine geplaatste berichten niet rechtstreeks uit deze meldingen halen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="1a4a0-117">Zie [Spammeldingen voor eindgebruikers in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="1a4a0-118">Berichten die in quarantaine zijn geplaatst voor phishing van vertrouwelijke informatie, malware of door e-mailstroomregels (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="1a4a0-119">Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="1a4a0-120">U kunt een bericht slechts eenmaal vrijgeven en melden als fout-positief (geen ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="1a4a0-121">Uw berichten in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="1a4a0-121">View your quarantined messages</span></span>

1. <span data-ttu-id="1a4a0-122">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="1a4a0-123">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="1a4a0-124">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="1a4a0-125">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="1a4a0-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="1a4a0-126">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-127">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-128">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-129">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-130">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-131">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-132">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1a4a0-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="1a4a0-133">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-133">**Recipient**</span></span>

   - <span data-ttu-id="1a4a0-134">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-134">**Message ID**</span></span>

   - <span data-ttu-id="1a4a0-135">**Beleidsnaam**: deze eigenschap toont het beleid waardoor het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-135">**Policy name**: This property shows the policy that caused the message to be quarantined.</span></span> <span data-ttu-id="1a4a0-136">U kunt deze gegevens aan uw beheerder doorgeven.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-136">You can give this information to your admin.</span></span>

   - <span data-ttu-id="1a4a0-137">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-137">**Size**</span></span>

   - <span data-ttu-id="1a4a0-138">**Richting**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-138">**Direction**</span></span>

   <span data-ttu-id="1a4a0-139">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="1a4a0-140">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1a4a0-141">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-141">The available filters are:</span></span>

   - <span data-ttu-id="1a4a0-142">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="1a4a0-143">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-143">**Today**</span></span>

     - <span data-ttu-id="1a4a0-144">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-144">**Next 2 days**</span></span>

     - <span data-ttu-id="1a4a0-145">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-145">**Next 7 days**</span></span>

     - <span data-ttu-id="1a4a0-146">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1a4a0-147">**Ontvangen op**: voer een **begindatum** en**einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1a4a0-148">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="1a4a0-149">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-149">**Bulk**</span></span>

     - <span data-ttu-id="1a4a0-150">**Spam**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-150">**Spam**</span></span>

     - <span data-ttu-id="1a4a0-151">**Phish** (vanaf april 2020)</span><span class="sxs-lookup"><span data-stu-id="1a4a0-151">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="1a4a0-152">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="1a4a0-153">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="1a4a0-154">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="1a4a0-155">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-155">Wildcards aren't supported.</span></span> <span data-ttu-id="1a4a0-156">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-156">You can search by the following values:</span></span>

   - <span data-ttu-id="1a4a0-157">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="1a4a0-158">Als u een bericht selecteert in de lijst, verschijnt de waarde **Bericht-ID** in het deelvenster **Details** dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="1a4a0-159">Beheerders kunnen [berichttracering](message-trace-scc.md) gebruiken om naar berichten en de bijbehorende bericht-ID’s te zoeken.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="1a4a0-160">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="1a4a0-161">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="1a4a0-162">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="1a4a0-163">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="1a4a0-164">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-164">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="1a4a0-165">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="1a4a0-166">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="1a4a0-166">Export message results</span></span>

1. <span data-ttu-id="1a4a0-167">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="1a4a0-168">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="1a4a0-169">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="1a4a0-170">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="1a4a0-170">View quarantined message details</span></span>

<span data-ttu-id="1a4a0-171">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1a4a0-172">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="1a4a0-173">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-173">**Sender address**</span></span>

- <span data-ttu-id="1a4a0-174">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="1a4a0-175">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="1a4a0-175">**Subject**</span></span>

- <span data-ttu-id="1a4a0-176">**Reden van quarantaine**: wordt getoond als een bericht is geïdentificeerd als **Spam**, **Bulk** of (vanaf april 2020) **Phish**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="1a4a0-177">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="1a4a0-178">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="1a4a0-179">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="1a4a0-180">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="1a4a0-181">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="1a4a0-181">Take action on quarantined email</span></span>

<span data-ttu-id="1a4a0-182">Nadat u een bericht selecteert, krijgt u in het deelvenster **Details** opties wat u met het bericht kunt doen:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1a4a0-183">**Bericht vrijgeven**: kies in het deelvenster dat wordt weergegeven of u **Berichten wilt rapporteren aan Microsoft voor analyse**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="1a4a0-184">Dit is standaard geselecteerd en rapporteert het bericht dat onterecht in quarantaine is geplaatst aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="1a4a0-185">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="1a4a0-186">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="1a4a0-187">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Office 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="1a4a0-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="1a4a0-188">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="1a4a0-189">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="1a4a0-190">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="1a4a0-191">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="1a4a0-192">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="1a4a0-193">**Verwijderen uit quarantaine**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="1a4a0-194">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="1a4a0-195">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="1a4a0-196">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="1a4a0-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="1a4a0-197">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="1a4a0-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="1a4a0-198">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="1a4a0-199">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="1a4a0-200">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="1a4a0-200">When you're finished, click **Close**.</span></span>
