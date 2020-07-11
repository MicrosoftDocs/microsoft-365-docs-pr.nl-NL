---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen in Exchange Online Protection (EOP) leren hoe ze in quarantaine geplaatste berichten voor alle gebruikers kunnen bekijken en beheren. Beheerders in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP) kunnen ook bestanden in quarantaine beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.openlocfilehash: 5e7c594669cf910404badd85c35671c284d4d91e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101679"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="db21a-104">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="db21a-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="db21a-105">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="db21a-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="db21a-106">Zie [EOP in quarantaine geplaatst](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db21a-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="db21a-107">Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers bekijken, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db21a-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="db21a-108">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstromen (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="db21a-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="db21a-109">Beheerders kunnen ook fout-positieven melden aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db21a-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="db21a-110">Beheerders in organisaties met Office 365 Advance Threat Protection (Office 365 ATP) kunnen ook in quarantaine geplaatste bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams bekijken, downloaden en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db21a-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="db21a-111">U bekijkt en beheert in quarantaine geplaatste berichten in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="db21a-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db21a-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="db21a-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db21a-113">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="db21a-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="db21a-114">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="db21a-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="db21a-115">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db21a-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="db21a-116">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db21a-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="db21a-117">U moet machtigingen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de **quarantainerol** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="db21a-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="db21a-118">Standaard wordt deze rol toegewezen aan de **rolgroepen Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="db21a-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="db21a-119">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="db21a-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="db21a-120">In quarantaine geplaatste berichten worden gedurende een standaardperiode bewaard voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="db21a-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="db21a-121">Berichten die in quarantaine zijn geplaatst via het antispambeleid (spam, phishing en bulke-mail): 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="db21a-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="db21a-122">Dit is de standaard- en maximale waarde.</span><span class="sxs-lookup"><span data-stu-id="db21a-122">This is the default and maximum value.</span></span> <span data-ttu-id="db21a-123">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="db21a-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="db21a-124">Berichten die malware bevatten: 15 dagen.</span><span class="sxs-lookup"><span data-stu-id="db21a-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="db21a-125">Wanneer een bericht uit quarantaine verloopt, u het bericht niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="db21a-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="db21a-126">Gebruik het Security & Compliance Center om e-mailberichten in quarantaine te beheren</span><span class="sxs-lookup"><span data-stu-id="db21a-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="db21a-127">E-mail in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="db21a-127">View quarantined email</span></span>

1. <span data-ttu-id="db21a-128">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="db21a-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="db21a-129">Controleer of **Weergave in quarantaine** is ingesteld op de **standaardwaarde-e-mail**.</span><span class="sxs-lookup"><span data-stu-id="db21a-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="db21a-130">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="db21a-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="db21a-131">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="db21a-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="db21a-132">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="db21a-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="db21a-133">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-134">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-135">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-136">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-137">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-138">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-139">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="db21a-139">**Recipient**</span></span>

   - <span data-ttu-id="db21a-140">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="db21a-140">**Message ID**</span></span>

   - <span data-ttu-id="db21a-141">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="db21a-141">**Policy name**</span></span>

   - <span data-ttu-id="db21a-142">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="db21a-142">**Size**</span></span>

   - <span data-ttu-id="db21a-143">**Richting**</span><span class="sxs-lookup"><span data-stu-id="db21a-143">**Direction**</span></span>

   <span data-ttu-id="db21a-144">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="db21a-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="db21a-145">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="db21a-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="db21a-146">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="db21a-146">The available filters are:</span></span>

   - <span data-ttu-id="db21a-147">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="db21a-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="db21a-148">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="db21a-148">**Today**</span></span>

     - <span data-ttu-id="db21a-149">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="db21a-149">**Next 2 days**</span></span>

     - <span data-ttu-id="db21a-150">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="db21a-150">**Next 7 days**</span></span>

     - <span data-ttu-id="db21a-151">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="db21a-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="db21a-152">**Ontvangen op**: voer een **begindatum** en**einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="db21a-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="db21a-153">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="db21a-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="db21a-154">**Beleid**: Het bericht voldeed aan de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="db21a-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="db21a-155">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="db21a-155">**Bulk**</span></span>

     - <span data-ttu-id="db21a-156">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="db21a-156">**Phish**</span></span>

     - <span data-ttu-id="db21a-157">**Malware**</span><span class="sxs-lookup"><span data-stu-id="db21a-157">**Malware**</span></span>

     - <span data-ttu-id="db21a-158">**Spam**</span><span class="sxs-lookup"><span data-stu-id="db21a-158">**Spam**</span></span>

     - <span data-ttu-id="db21a-159">**Hoog vertrouwen Phish**</span><span class="sxs-lookup"><span data-stu-id="db21a-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="db21a-160">**E-mailontvanger:** Alle gebruikers of alleen berichten die naar u worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="db21a-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="db21a-161">Eindgebruikers kunnen alleen berichten in quarantaine beheren die naar hen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="db21a-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="db21a-162">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="db21a-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="db21a-163">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="db21a-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="db21a-164">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="db21a-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="db21a-165">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="db21a-165">Wildcards aren't supported.</span></span> <span data-ttu-id="db21a-166">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="db21a-166">You can search by the following values:</span></span>

   - <span data-ttu-id="db21a-167">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="db21a-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="db21a-168">U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van geleverd.</span><span class="sxs-lookup"><span data-stu-id="db21a-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="db21a-169">Zorg ervoor dat u de volledige waarde van de bericht-ID opneemt, die hoekbeugels () kan \<\> bevatten.</span><span class="sxs-lookup"><span data-stu-id="db21a-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="db21a-170">Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="db21a-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="db21a-171">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="db21a-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="db21a-172">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="db21a-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="db21a-173">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="db21a-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="db21a-174">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="db21a-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="db21a-175">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="db21a-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="db21a-176">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="db21a-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="db21a-177">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="db21a-177">Export message results</span></span>

1. <span data-ttu-id="db21a-178">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="db21a-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="db21a-179">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="db21a-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="db21a-180">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="db21a-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="db21a-181">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="db21a-181">View quarantined message details</span></span>

<span data-ttu-id="db21a-182">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="db21a-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="db21a-183">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="db21a-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="db21a-184">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="db21a-184">**Sender address**</span></span>

- <span data-ttu-id="db21a-185">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="db21a-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="db21a-186">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="db21a-186">**Subject**</span></span>

- <span data-ttu-id="db21a-187">**Quarantainereden**: geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeenkomen met een mailflowregel **(Transportregel),** of is geïdentificeerd als malware **.**</span><span class="sxs-lookup"><span data-stu-id="db21a-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="db21a-188">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="db21a-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="db21a-189">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="db21a-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="db21a-190">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="db21a-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="db21a-191">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="db21a-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="db21a-192">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="db21a-192">Take action on quarantined email</span></span>

<span data-ttu-id="db21a-193">Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in het flyoutvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="db21a-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="db21a-194">**Releasebericht**: Kies in het flyout-deelvenster dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="db21a-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="db21a-195">**Berichten rapporteren aan Microsoft voor analyse:** dit is standaard geselecteerd en rapporteert het foutieve bericht in quarantaine aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="db21a-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="db21a-196">Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="db21a-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="db21a-197">Afhankelijk van hun analyse kunnen de regels voor het hele spamfilter voor de hele service worden aangepast om het bericht door te laten.</span><span class="sxs-lookup"><span data-stu-id="db21a-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="db21a-198">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="db21a-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="db21a-199">**Berichten vrijgeven aan alle ontvangers**</span><span class="sxs-lookup"><span data-stu-id="db21a-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="db21a-200">**Berichten vrijgeven aan specifieke ontvangers**</span><span class="sxs-lookup"><span data-stu-id="db21a-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="db21a-201">**Berichten vrijgeven aan andere mensen**</span><span class="sxs-lookup"><span data-stu-id="db21a-201">**Release messages to other people**</span></span>

  <span data-ttu-id="db21a-202">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="db21a-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="db21a-203">Opmerkingen over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="db21a-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="db21a-204">U een bericht niet meer dan één keer aan dezelfde ontvanger vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="db21a-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="db21a-205">Alleen ontvangers die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële ontvangers.</span><span class="sxs-lookup"><span data-stu-id="db21a-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="db21a-206">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="db21a-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="db21a-207">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="db21a-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="db21a-208">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="db21a-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="db21a-209">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="db21a-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="db21a-210">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="db21a-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="db21a-211">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="db21a-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="db21a-212">**Uit quarantaine verwijderen**: Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="db21a-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="db21a-213">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="db21a-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="db21a-214">**Bericht verzenden**: Kies in het flyout-deelvenster dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="db21a-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="db21a-215">**Objecttype**: **E-mail** (standaard), **URL**of **Bijlage**.</span><span class="sxs-lookup"><span data-stu-id="db21a-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="db21a-216">**Inzendingsvorm**: **netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand).</span><span class="sxs-lookup"><span data-stu-id="db21a-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="db21a-217">Als u **Bestand** selecteert en **vervolgens Netwerkbericht-id**selecteert, is de oorspronkelijke waarde verdwenen.</span><span class="sxs-lookup"><span data-stu-id="db21a-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="db21a-218">**Geadresseerden**: typ bij leasen van één oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle ontvangers te identificeren.</span><span class="sxs-lookup"><span data-stu-id="db21a-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="db21a-219">U ook op **Alles selecteren** klikken en vervolgens selectief afzonderlijke ontvangers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db21a-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="db21a-220">**Reden voor indiening**: **Had niet geblokkeerd mogen worden** (standaard) of geblokkeerd moeten **worden.**</span><span class="sxs-lookup"><span data-stu-id="db21a-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="db21a-221">Klik op **Verzenden**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="db21a-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="db21a-222">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="db21a-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="db21a-223">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="db21a-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="db21a-224">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="db21a-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="db21a-225">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="db21a-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="db21a-226">Houd rekening met het volgende scenario: john@gmail.com stuurt een bericht naar faith@contoso.com en john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="db21a-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="db21a-227">Gmail bifurcates dit bericht in twee exemplaren die beide zijn doorgestuurd naar quarantaine als phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db21a-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="db21a-228">Een beheerder geeft beide berichten vrij om te admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="db21a-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="db21a-229">Het eerste vrijgegeven bericht dat het beheerderspostvak bereikt, wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="db21a-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="db21a-230">Het tweede vrijgegeven bericht wordt geïdentificeerd als dubbele levering en wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="db21a-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="db21a-231">Bericht worden geïdentificeerd als duplicaten als ze dezelfde bericht-ID en ontvangen tijd hebben.</span><span class="sxs-lookup"><span data-stu-id="db21a-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="db21a-232">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="db21a-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="db21a-233">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="db21a-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="db21a-234">Alleen ATP: gebruik het Security & Compliance Center om in quarantaine geplaatste bestanden te beheren</span><span class="sxs-lookup"><span data-stu-id="db21a-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="db21a-235">De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor ATP-abonnement 1- en Plan 2-abonnees.</span><span class="sxs-lookup"><span data-stu-id="db21a-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="db21a-236">In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="db21a-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="db21a-237">Bestanden in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="db21a-237">View quarantined files</span></span>

1. <span data-ttu-id="db21a-238">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="db21a-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="db21a-239">**Weergave wijzigen die in quarantaine is geplaatst** in de standaardwaardebestanden . **files**</span><span class="sxs-lookup"><span data-stu-id="db21a-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="db21a-240">U sorteren op een veld door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="db21a-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="db21a-241">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="db21a-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="db21a-242">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="db21a-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="db21a-243">De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="db21a-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="db21a-244">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-245">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-246">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-247">**BESTANDS-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-248">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-249">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-250">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="db21a-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="db21a-251">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="db21a-251">**Detected by**</span></span>

   - <span data-ttu-id="db21a-252">**Gewijzigd op tijd**</span><span class="sxs-lookup"><span data-stu-id="db21a-252">**Modified by time**</span></span>

4. <span data-ttu-id="db21a-253">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="db21a-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="db21a-254">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="db21a-254">The available filters are:</span></span>

   - <span data-ttu-id="db21a-255">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="db21a-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="db21a-256">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="db21a-256">**Today**</span></span>

     - <span data-ttu-id="db21a-257">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="db21a-257">**Next 2 days**</span></span>

     - <span data-ttu-id="db21a-258">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="db21a-258">**Next 7 days**</span></span>

     - <span data-ttu-id="db21a-259">Een aangepast datum-tijdbereik.</span><span class="sxs-lookup"><span data-stu-id="db21a-259">A custom date/time range.</span></span>

   - <span data-ttu-id="db21a-260">**Ontvangen tijd**</span><span class="sxs-lookup"><span data-stu-id="db21a-260">**Received time**</span></span>

   - <span data-ttu-id="db21a-261">**Quarantaine reden:** De enige beschikbare waarde is **Malware**.</span><span class="sxs-lookup"><span data-stu-id="db21a-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="db21a-262">Nadat u een specifiek in quarantaine geplaatst bestand hebt gevonden, selecteert u het bestand om er details over te bekijken en actie te ondernemen (bijvoorbeeld het bericht weergeven, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="db21a-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="db21a-263">Bestandsresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="db21a-263">Export file results</span></span>

1. <span data-ttu-id="db21a-264">Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="db21a-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="db21a-265">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="db21a-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="db21a-266">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="db21a-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="db21a-267">Bestandsgegevens in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="db21a-267">View quarantined file details</span></span>

<span data-ttu-id="db21a-268">Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsdetails weergegeven in het flyoutvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="db21a-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="db21a-269">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="db21a-269">**File Name**</span></span>

- <span data-ttu-id="db21a-270">**BESTANDS-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="db21a-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="db21a-271">**Schadelijke inhoud gedetecteerd op** De datum/tijd dat het bestand in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="db21a-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="db21a-272">**Verloopt**: de datum waarop het bestand uit quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db21a-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="db21a-273">**Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.</span><span class="sxs-lookup"><span data-stu-id="db21a-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="db21a-274">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="db21a-274">**Released?**</span></span>

- <span data-ttu-id="db21a-275">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="db21a-275">**Malware Name**</span></span>

- <span data-ttu-id="db21a-276">**Document-id**: een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="db21a-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="db21a-277">**Bestandsgrootte**: In kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="db21a-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="db21a-278">**Organisatie** De unieke ID van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="db21a-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="db21a-279">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="db21a-279">**Last modified**</span></span>

- <span data-ttu-id="db21a-280">**Gewijzigd door**: De gebruiker die het bestand voor het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="db21a-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="db21a-281">**Secure Hash Algorithm 256-bits (SHA-256) waarde**: U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="db21a-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="db21a-282">Actie ondernemen op in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="db21a-282">Take action on quarantined files</span></span>

<span data-ttu-id="db21a-283">Wanneer u een bestand in de lijst selecteert, u de volgende acties uitvoeren in het bestand in het flyoutvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="db21a-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="db21a-284">**Bestanden vrijgeven**: Selecteer (standaard) of schakel **Rapportbestanden uit voor Analyse**en klik op Bestanden **vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="db21a-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="db21a-285">**Bestand downloaden**</span><span class="sxs-lookup"><span data-stu-id="db21a-285">**Download file**</span></span>

- <span data-ttu-id="db21a-286">**Bestand uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="db21a-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="db21a-287">Als u de bestanden niet vrijlaat of verwijdert, worden ze verwijderd nadat de standaardretentieperiode voor quarantaine is verstreken.</span><span class="sxs-lookup"><span data-stu-id="db21a-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="db21a-288">Acties op meerdere bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="db21a-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="db21a-289">Wanneer u meerdere bestanden in quarantaine in de lijst selecteert (maximaal 100), wordt het flyoutvenster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="db21a-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="db21a-290">**Bestanden vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="db21a-290">**Release files**</span></span>

- <span data-ttu-id="db21a-291">**Bestanden verwijderen**: Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="db21a-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="db21a-292">Meld u aan en [ga naar het Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)met algemene beheerdersrechten (of de juiste rollen security & Compliance Center) in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="db21a-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="db21a-293">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om berichten en bestanden in quarantaine te bekijken en te beheren</span><span class="sxs-lookup"><span data-stu-id="db21a-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="db21a-294">De cmdlets die u gebruikt om berichten en bestanden in quarantaine te bekijken en te beheren zijn:</span><span class="sxs-lookup"><span data-stu-id="db21a-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="db21a-295">Bericht in quarantaine verwijderen</span><span class="sxs-lookup"><span data-stu-id="db21a-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="db21a-296">In quarantaine exporterenMessage</span><span class="sxs-lookup"><span data-stu-id="db21a-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="db21a-297">In quarantaine plaatsenMessage</span><span class="sxs-lookup"><span data-stu-id="db21a-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="db21a-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Houd er rekening mee dat deze cmdlet alleen is voor berichten, niet voor malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.</span><span class="sxs-lookup"><span data-stu-id="db21a-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="db21a-299">Release-quarantineMessage</span><span class="sxs-lookup"><span data-stu-id="db21a-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
