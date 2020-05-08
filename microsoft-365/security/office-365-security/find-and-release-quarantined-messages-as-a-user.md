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
description: In dit artikel leert u hoe u in quarantaine geplaatste berichten kunt weergeven en beheren in het Beveiligings- en compliancecentrum van Microsoft 365.
ms.openlocfilehash: 177f60f1fccc764d74ec0374249a62c602cb84aa
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036510"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="10a45-103">Berichten in quarantaine zoeken en vrijgeven als gebruiker</span><span class="sxs-lookup"><span data-stu-id="10a45-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="10a45-104">Potentieel gevaarlijke of ongewenste berichten worden in quarantaine geplaatst in Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="10a45-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="10a45-105">Zie [Quarantaine in Office 365](quarantine-email-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10a45-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="10a45-106">Als gebruiker kunt u uw berichten in quarantaine waarvan u ontvanger bent en het bericht in quarantaine werd geplaatst als spam, bulkmail of (vanaf april 2020) phishing, zien, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="10a45-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="10a45-107">U kunt uw in quarantaine geplaatste berichten weergeven en beheren in het beveiligings- en compliancecentrum of (als een beheerder dit heeft ingesteld) in [spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="10a45-107">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="10a45-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="10a45-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="10a45-109">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="10a45-109">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="10a45-110">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="10a45-110">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="10a45-111">Beheerders kunnen instellen hoe lang berichten in quarantaine blijven voordat ze permanent worden verwijderd (antispambeleid).</span><span class="sxs-lookup"><span data-stu-id="10a45-111">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="10a45-112">Berichten waarvan de quarantaine is verlopen, kunnen niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="10a45-112">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="10a45-113">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10a45-113">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="10a45-114">Beheerders kunnen ook [Spammeldingen voor eindgebruikers inschakelen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="10a45-114">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="10a45-115">Gebruikers kunnen ongewenste, in quarantaine geplaatste berichten vrijgeven, maar in quarantaine geplaatste berichten niet rechtstreeks uit deze meldingen halen.</span><span class="sxs-lookup"><span data-stu-id="10a45-115">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="10a45-116">Zie [Spammeldingen voor eindgebruikers in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="10a45-116">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="10a45-117">Berichten die in quarantaine zijn geplaatst voor phishing van vertrouwelijke informatie, malware of door e-mailstroomregels (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="10a45-117">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="10a45-118">Phishingberichten kunnen door gebruikers worden bekeken, maar alleen worden vrijgegeven door beheerders.</span><span class="sxs-lookup"><span data-stu-id="10a45-118">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="10a45-119">Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="10a45-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="10a45-120">U kunt een bericht slechts eenmaal vrijgeven en melden als fout-positief (geen ongewenste e-mail).</span><span class="sxs-lookup"><span data-stu-id="10a45-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="10a45-121">Uw berichten in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="10a45-121">View your quarantined messages</span></span>

1. <span data-ttu-id="10a45-122">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="10a45-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="10a45-123">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="10a45-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="10a45-124">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="10a45-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="10a45-125">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="10a45-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="10a45-126">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-127">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-128">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-129">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-130">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-131">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-132">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="10a45-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="10a45-133">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="10a45-133">**Recipient**</span></span>

   - <span data-ttu-id="10a45-134">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="10a45-134">**Message ID**</span></span>

   - <span data-ttu-id="10a45-135">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="10a45-135">**Policy name**</span></span>

   - <span data-ttu-id="10a45-136">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="10a45-136">**Size**</span></span>

   - <span data-ttu-id="10a45-137">**Richting**</span><span class="sxs-lookup"><span data-stu-id="10a45-137">**Direction**</span></span>

   <span data-ttu-id="10a45-138">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="10a45-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="10a45-139">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="10a45-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="10a45-140">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="10a45-140">The available filters are:</span></span>

   - <span data-ttu-id="10a45-141">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="10a45-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="10a45-142">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="10a45-142">**Today**</span></span>

     - <span data-ttu-id="10a45-143">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="10a45-143">**Next 2 days**</span></span>

     - <span data-ttu-id="10a45-144">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="10a45-144">**Next 7 days**</span></span>

     - <span data-ttu-id="10a45-145">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="10a45-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="10a45-146">**Ontvangen op**: voer een **begindatum** en**einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="10a45-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="10a45-147">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="10a45-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="10a45-148">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="10a45-148">**Bulk**</span></span>

     - <span data-ttu-id="10a45-149">**Spam**</span><span class="sxs-lookup"><span data-stu-id="10a45-149">**Spam**</span></span>

     - <span data-ttu-id="10a45-150">**Phish** (vanaf april 2020)</span><span class="sxs-lookup"><span data-stu-id="10a45-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="10a45-151">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="10a45-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="10a45-152">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="10a45-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="10a45-153">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="10a45-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="10a45-154">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="10a45-154">Wildcards aren't supported.</span></span> <span data-ttu-id="10a45-155">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="10a45-155">You can search by the following values:</span></span>

   - <span data-ttu-id="10a45-156">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="10a45-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="10a45-157">Als u een bericht selecteert in de lijst, verschijnt de waarde **Bericht-ID** in het deelvenster **Details** dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="10a45-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="10a45-158">Beheerders kunnen [berichttracering](message-trace-scc.md) gebruiken om naar berichten en de bijbehorende bericht-ID’s te zoeken.</span><span class="sxs-lookup"><span data-stu-id="10a45-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="10a45-159">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="10a45-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="10a45-160">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="10a45-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="10a45-161">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="10a45-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="10a45-162">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="10a45-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="10a45-163">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="10a45-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="10a45-164">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="10a45-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="10a45-165">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="10a45-165">Export message results</span></span>

1. <span data-ttu-id="10a45-166">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="10a45-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="10a45-167">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="10a45-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="10a45-168">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="10a45-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="10a45-169">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="10a45-169">View quarantined message details</span></span>

<span data-ttu-id="10a45-170">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="10a45-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="10a45-171">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="10a45-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="10a45-172">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="10a45-172">**Sender address**</span></span>

- <span data-ttu-id="10a45-173">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="10a45-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="10a45-174">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="10a45-174">**Subject**</span></span>

- <span data-ttu-id="10a45-175">**Reden van quarantaine**: wordt getoond als een bericht is geïdentificeerd als **Spam**, **Bulk** of (vanaf april 2020) **Phish**.</span><span class="sxs-lookup"><span data-stu-id="10a45-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="10a45-176">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="10a45-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="10a45-177">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="10a45-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="10a45-178">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="10a45-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="10a45-179">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="10a45-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="10a45-180">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="10a45-180">Take action on quarantined email</span></span>

<span data-ttu-id="10a45-181">Nadat u een bericht selecteert, krijgt u in het deelvenster **Details** opties wat u met het bericht kunt doen:</span><span class="sxs-lookup"><span data-stu-id="10a45-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="10a45-182">**Bericht vrijgeven**: kies in het deelvenster dat wordt weergegeven of u **Berichten wilt rapporteren aan Microsoft voor analyse**.</span><span class="sxs-lookup"><span data-stu-id="10a45-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="10a45-183">Dit is standaard geselecteerd en rapporteert het bericht dat onterecht in quarantaine is geplaatst aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="10a45-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="10a45-184">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="10a45-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="10a45-185">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="10a45-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="10a45-186">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="10a45-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="10a45-187">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="10a45-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="10a45-188">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="10a45-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="10a45-189">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="10a45-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="10a45-190">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="10a45-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="10a45-191">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="10a45-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="10a45-192">**Verwijderen uit quarantaine**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="10a45-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="10a45-193">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="10a45-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="10a45-194">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="10a45-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="10a45-195">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="10a45-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="10a45-196">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="10a45-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="10a45-197">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="10a45-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="10a45-198">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="10a45-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="10a45-199">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="10a45-199">When you're finished, click **Close**.</span></span>
