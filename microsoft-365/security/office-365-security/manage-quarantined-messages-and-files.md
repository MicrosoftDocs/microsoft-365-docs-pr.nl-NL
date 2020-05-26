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
description: Beheerders kunnen leren hoe ze in quarantaine geplaatste berichten kunnen bekijken en beheren voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP) kunnen ook in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.openlocfilehash: 521268d291c73cc94e8be87f1f2896a17c623678
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352418"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="195e7-104">Berichten en bestanden in quarantaine beheren als EOP-beheerder</span><span class="sxs-lookup"><span data-stu-id="195e7-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="195e7-105">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="195e7-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="195e7-106">Zie [In quarantaine geplaatste e-mailberichten in EOP](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="195e7-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="195e7-107">Beheerders kunnen alle soorten in quarantaine geplaatste berichten voor alle gebruikers bekijken, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="195e7-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="195e7-108">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="195e7-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="195e7-109">Beheerders kunnen ook fout-positieven melden aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="195e7-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="195e7-110">Beheerders in organisaties met Office 365 Advance Threat Protection (Office 365 ATP) kunnen ook in quarantaine geplaatste bestanden bekijken, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="195e7-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="195e7-111">U bekijkt en beheert in quarantaine geplaatste berichten in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="195e7-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="195e7-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="195e7-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="195e7-113">Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="195e7-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="195e7-114">Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.</span><span class="sxs-lookup"><span data-stu-id="195e7-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="195e7-115">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="195e7-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="195e7-116">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="195e7-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="195e7-117">U moet machtigingen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de functie **Quarantaine** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="195e7-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="195e7-118">Deze rol is standaard toegewezen aan de rolgroepen **Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Beveiligingscentrum & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="195e7-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="195e7-119">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="195e7-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="195e7-120">In quarantaine geplaatste berichten worden standaard bewaard voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="195e7-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="195e7-121">Berichten in quarantaine geplaatst door antispambeleid (spam, phishing en bulke-mail): 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="195e7-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="195e7-122">Dit is de standaard- en maximale waarde.</span><span class="sxs-lookup"><span data-stu-id="195e7-122">This is the default and maximum value.</span></span> <span data-ttu-id="195e7-123">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)om deze waarde te configureren.</span><span class="sxs-lookup"><span data-stu-id="195e7-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="195e7-124">Berichten die malware bevatten: 15 dagen.</span><span class="sxs-lookup"><span data-stu-id="195e7-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="195e7-125">Wanneer een bericht uit quarantaine verloopt, u het bericht niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="195e7-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="195e7-126">Het Beveiligings& Compliance Center gebruiken om in quarantaine geplaatste e-mailberichten te beheren</span><span class="sxs-lookup"><span data-stu-id="195e7-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="195e7-127">In quarantaine geplaatste e-mail weergeven</span><span class="sxs-lookup"><span data-stu-id="195e7-127">View quarantined email</span></span>

1. <span data-ttu-id="195e7-128">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="195e7-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="195e7-129">Controleer of **Weergave in quarantaine** is ingesteld op de **standaardwaarde-e-mail**.</span><span class="sxs-lookup"><span data-stu-id="195e7-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="195e7-130">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="195e7-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="195e7-131">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="195e7-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="195e7-132">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="195e7-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="195e7-133">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-134">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-135">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-136">**Reden van quarantaine**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-137">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-138">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-139">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="195e7-139">**Recipient**</span></span>

   - <span data-ttu-id="195e7-140">**Bericht-ID**</span><span class="sxs-lookup"><span data-stu-id="195e7-140">**Message ID**</span></span>

   - <span data-ttu-id="195e7-141">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="195e7-141">**Policy name**</span></span>

   - <span data-ttu-id="195e7-142">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="195e7-142">**Size**</span></span>

   - <span data-ttu-id="195e7-143">**Richting**</span><span class="sxs-lookup"><span data-stu-id="195e7-143">**Direction**</span></span>

   <span data-ttu-id="195e7-144">Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="195e7-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="195e7-145">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="195e7-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="195e7-146">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="195e7-146">The available filters are:</span></span>

   - <span data-ttu-id="195e7-147">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="195e7-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="195e7-148">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="195e7-148">**Today**</span></span>

     - <span data-ttu-id="195e7-149">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="195e7-149">**Next 2 days**</span></span>

     - <span data-ttu-id="195e7-150">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="195e7-150">**Next 7 days**</span></span>

     - <span data-ttu-id="195e7-151">**Aangepast**: voer een **begindatum** en **einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="195e7-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="195e7-152">**Ontvangen op**: voer een **begindatum** en**einddatum** in.</span><span class="sxs-lookup"><span data-stu-id="195e7-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="195e7-153">**Reden van quarantaine**:</span><span class="sxs-lookup"><span data-stu-id="195e7-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="195e7-154">**Beleid:** het bericht kwam overeen met de voorwaarden van een regel voor e-mailstroom (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="195e7-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="195e7-155">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="195e7-155">**Bulk**</span></span>

     - <span data-ttu-id="195e7-156">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="195e7-156">**Phish**</span></span>

     - <span data-ttu-id="195e7-157">**Malware**</span><span class="sxs-lookup"><span data-stu-id="195e7-157">**Malware**</span></span>

     - <span data-ttu-id="195e7-158">**Spam**</span><span class="sxs-lookup"><span data-stu-id="195e7-158">**Spam**</span></span>

     - <span data-ttu-id="195e7-159">**Hoog vertrouwen Phish**</span><span class="sxs-lookup"><span data-stu-id="195e7-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="195e7-160">**E-mailontvanger:** alle gebruikers of alleen berichten die naar u worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="195e7-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="195e7-161">Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="195e7-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="195e7-162">Als u het filter wilt wissen, drukt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="195e7-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="195e7-163">Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="195e7-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="195e7-164">Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken.</span><span class="sxs-lookup"><span data-stu-id="195e7-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="195e7-165">Jokertekens worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="195e7-165">Wildcards aren't supported.</span></span> <span data-ttu-id="195e7-166">U kunt zoeken op een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="195e7-166">You can search by the following values:</span></span>

   - <span data-ttu-id="195e7-167">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="195e7-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="195e7-168">U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van geleverd.</span><span class="sxs-lookup"><span data-stu-id="195e7-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="195e7-169">Zorg ervoor dat u de volledige bericht-ID-waarde opneemt, waaronder mogelijk hoekhaakjes ( \< \> ).</span><span class="sxs-lookup"><span data-stu-id="195e7-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="195e7-170">Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="195e7-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="195e7-171">**E-mailadres afzender**: een enkel e-mailadres van een afzender.</span><span class="sxs-lookup"><span data-stu-id="195e7-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="195e7-172">**E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.</span><span class="sxs-lookup"><span data-stu-id="195e7-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="195e7-173">**Onderwerp**: gebruik het volledige onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="195e7-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="195e7-174">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="195e7-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="195e7-175">Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="195e7-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="195e7-176">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="195e7-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="195e7-177">Berichtresultaat exporteren</span><span class="sxs-lookup"><span data-stu-id="195e7-177">Export message results</span></span>

1. <span data-ttu-id="195e7-178">Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="195e7-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="195e7-179">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="195e7-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="195e7-180">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="195e7-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="195e7-181">Gegevens van bericht in quarantaine bekijken</span><span class="sxs-lookup"><span data-stu-id="195e7-181">View quarantined message details</span></span>

<span data-ttu-id="195e7-182">Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:</span><span class="sxs-lookup"><span data-stu-id="195e7-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="195e7-183">**Bericht-ID**: de wereldwijd unieke identificatie van het bericht.</span><span class="sxs-lookup"><span data-stu-id="195e7-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="195e7-184">**Adres afzender**</span><span class="sxs-lookup"><span data-stu-id="195e7-184">**Sender address**</span></span>

- <span data-ttu-id="195e7-185">**Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="195e7-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="195e7-186">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="195e7-186">**Subject**</span></span>

- <span data-ttu-id="195e7-187">**Quarantainereden:** geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish,** een e-mailstroomregel **(transportregel)** of is geïdentificeerd als **malware**.</span><span class="sxs-lookup"><span data-stu-id="195e7-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="195e7-188">**Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.</span><span class="sxs-lookup"><span data-stu-id="195e7-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="195e7-189">**Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.</span><span class="sxs-lookup"><span data-stu-id="195e7-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="195e7-190">**Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="195e7-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="195e7-191">**Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="195e7-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="195e7-192">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="195e7-192">Take action on quarantined email</span></span>

<span data-ttu-id="195e7-193">Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u met de berichten moet doen in het deelvenster **Flyout Details:**</span><span class="sxs-lookup"><span data-stu-id="195e7-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="195e7-194">**Releasebericht:** kies in het deelvenster flyout dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="195e7-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="195e7-195">**Berichten rapporteren aan Microsoft voor analyse:** dit is standaard geselecteerd en rapporteert het ten onrechte in quarantaine geplaatste bericht aan Microsoft als een fout-positief.</span><span class="sxs-lookup"><span data-stu-id="195e7-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="195e7-196">Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="195e7-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="195e7-197">Afhankelijk van hun analyse kunnen de regels voor spamfilters voor de hele service worden aangepast om het bericht door te laten gaan.</span><span class="sxs-lookup"><span data-stu-id="195e7-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="195e7-198">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="195e7-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="195e7-199">**Berichten vrijgeven aan alle ontvangers**</span><span class="sxs-lookup"><span data-stu-id="195e7-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="195e7-200">**Berichten vrijgeven aan specifieke ontvangers**</span><span class="sxs-lookup"><span data-stu-id="195e7-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="195e7-201">**Berichten vrijgeven aan andere mensen**</span><span class="sxs-lookup"><span data-stu-id="195e7-201">**Release messages to other people**</span></span>

  <span data-ttu-id="195e7-202">Klik op **Berichten vrijgeven** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="195e7-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="195e7-203">Opmerkingen over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="195e7-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="195e7-204">U een bericht niet meer dan één keer aan dezelfde ontvanger vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="195e7-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="195e7-205">Alleen ontvangers die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële ontvangers.</span><span class="sxs-lookup"><span data-stu-id="195e7-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="195e7-206">**Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken.</span><span class="sxs-lookup"><span data-stu-id="195e7-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="195e7-207">Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="195e7-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="195e7-208">Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:</span><span class="sxs-lookup"><span data-stu-id="195e7-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="195e7-209">**Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="195e7-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="195e7-210">**Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.</span><span class="sxs-lookup"><span data-stu-id="195e7-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="195e7-211">**Tekstweergave**: toont het bericht in gewone tekst.</span><span class="sxs-lookup"><span data-stu-id="195e7-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="195e7-212">**Uit quarantaine verwijderen**: Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="195e7-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="195e7-213">**Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="195e7-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="195e7-214">**Bericht verzenden:** kies in het deelvenster flyout dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="195e7-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="195e7-215">**Objecttype**: **E-mail** (standaard), **URL**of **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="195e7-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="195e7-216">**Indieningsindeling**: **Netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand).</span><span class="sxs-lookup"><span data-stu-id="195e7-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="195e7-217">Houd er rekening mee dat als u **Bestand** selecteert en vervolgens **Netwerkbericht-id**selecteert, de oorspronkelijke waarde is verdwenen.</span><span class="sxs-lookup"><span data-stu-id="195e7-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="195e7-218">**Ontvangers**: Typ bij lease een oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle geadresseerden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="195e7-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="195e7-219">U ook op **Alles selecteren** klikken en vervolgens afzonderlijke ontvangers selectief verwijderen.</span><span class="sxs-lookup"><span data-stu-id="195e7-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="195e7-220">**Reden voor indiening**: **Had niet moeten worden geblokkeerd** (standaard) of had moeten worden **geblokkeerd**.</span><span class="sxs-lookup"><span data-stu-id="195e7-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="195e7-221">Klik op **Verzenden als**u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="195e7-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="195e7-222">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.</span><span class="sxs-lookup"><span data-stu-id="195e7-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="195e7-223">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="195e7-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="195e7-224">Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="195e7-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="195e7-225">**Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.</span><span class="sxs-lookup"><span data-stu-id="195e7-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="195e7-226">**Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="195e7-226">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="195e7-227">Klik op **Sluiten** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="195e7-227">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="195e7-228">Alleen ATP: het Beveiligingscentrum & compliance gebruiken om in quarantaine geplaatste bestanden te beheren</span><span class="sxs-lookup"><span data-stu-id="195e7-228">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="195e7-229">De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor abonnees van ATP Plan 1 en Plan 2.</span><span class="sxs-lookup"><span data-stu-id="195e7-229">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="195e7-230">In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="195e7-230">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="195e7-231">In quarantaine geplaatste bestanden weergeven</span><span class="sxs-lookup"><span data-stu-id="195e7-231">View quarantined files</span></span>

1. <span data-ttu-id="195e7-232">Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.</span><span class="sxs-lookup"><span data-stu-id="195e7-232">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="195e7-233">**Weergave wijzigen in quarantaine geplaatst** in de standaardwaardebestanden . **files**</span><span class="sxs-lookup"><span data-stu-id="195e7-233">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="195e7-234">U sorteren op een veld door te klikken op een beschikbare kolomkop.</span><span class="sxs-lookup"><span data-stu-id="195e7-234">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="195e7-235">U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="195e7-235">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="195e7-236">Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien.</span><span class="sxs-lookup"><span data-stu-id="195e7-236">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="195e7-237">De standaardkolommen zijn gemarkeerd met een sterretje <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="195e7-237">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="195e7-238">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-238">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-239">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-239">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-240">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-240">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-241">**URL van bestand**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-241">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-242">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-242">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-243">**Vervalt op**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-243">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-244">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="195e7-244">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="195e7-245">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="195e7-245">**Detected by**</span></span>

   - <span data-ttu-id="195e7-246">**Gewijzigd door tijd**</span><span class="sxs-lookup"><span data-stu-id="195e7-246">**Modified by time**</span></span>

4. <span data-ttu-id="195e7-247">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="195e7-247">To filter the results, click **Filter**.</span></span> <span data-ttu-id="195e7-248">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="195e7-248">The available filters are:</span></span>

   - <span data-ttu-id="195e7-249">**Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:</span><span class="sxs-lookup"><span data-stu-id="195e7-249">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="195e7-250">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="195e7-250">**Today**</span></span>

     - <span data-ttu-id="195e7-251">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="195e7-251">**Next 2 days**</span></span>

     - <span data-ttu-id="195e7-252">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="195e7-252">**Next 7 days**</span></span>

     - <span data-ttu-id="195e7-253">Een aangepast datum-/tijdbereik.</span><span class="sxs-lookup"><span data-stu-id="195e7-253">A custom date/time range.</span></span>

   - <span data-ttu-id="195e7-254">**Ontvangen tijd**</span><span class="sxs-lookup"><span data-stu-id="195e7-254">**Received time**</span></span>

   - <span data-ttu-id="195e7-255">**Quarantaine reden:** De enige beschikbare waarde is **Malware**.</span><span class="sxs-lookup"><span data-stu-id="195e7-255">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="195e7-256">Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om details erover weer te geven en actie te ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="195e7-256">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="195e7-257">Bestandsresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="195e7-257">Export file results</span></span>

1. <span data-ttu-id="195e7-258">Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="195e7-258">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="195e7-259">Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="195e7-259">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="195e7-260">Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="195e7-260">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="195e7-261">Bestandsgegevens in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="195e7-261">View quarantined file details</span></span>

<span data-ttu-id="195e7-262">Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsdetails weergegeven in het flyout-deelvenster **Details:**</span><span class="sxs-lookup"><span data-stu-id="195e7-262">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="195e7-263">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="195e7-263">**File Name**</span></span>

- <span data-ttu-id="195e7-264">**URL van het bestand:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="195e7-264">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="195e7-265">**Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="195e7-265">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="195e7-266">**Verloopt:** de datum waarop het bestand uit quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="195e7-266">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="195e7-267">**Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.</span><span class="sxs-lookup"><span data-stu-id="195e7-267">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="195e7-268">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="195e7-268">**Released?**</span></span>

- <span data-ttu-id="195e7-269">**Naam malware**</span><span class="sxs-lookup"><span data-stu-id="195e7-269">**Malware Name**</span></span>

- <span data-ttu-id="195e7-270">**Document-id:** een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="195e7-270">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="195e7-271">**Bestandsgrootte**: In kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="195e7-271">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="195e7-272">**Organisatie** De unieke ID van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="195e7-272">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="195e7-273">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="195e7-273">**Last modified**</span></span>

- <span data-ttu-id="195e7-274">**Gewijzigd door**: De gebruiker die het bestand voor het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="195e7-274">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="195e7-275">**Waarde voor Secure Hash Algorithm (SHA-256):** U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="195e7-275">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="195e7-276">Actie ondernemen voor in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="195e7-276">Take action on quarantined files</span></span>

<span data-ttu-id="195e7-277">Wanneer u een bestand in de lijst selecteert, u de volgende acties in het bestand uitvoeren in het deelvenster **Flyout Details:**</span><span class="sxs-lookup"><span data-stu-id="195e7-277">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="195e7-278">**Bestanden vrijgeven**: Selecteer (standaard) of schakel De optie **Bestanden rapporteren aan Microsoft uit voor analyse**en klik op Bestanden **vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="195e7-278">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="195e7-279">**Bestand downloaden**</span><span class="sxs-lookup"><span data-stu-id="195e7-279">**Download file**</span></span>

- <span data-ttu-id="195e7-280">**Bestand uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="195e7-280">**Remove file from quarantine**</span></span>

<span data-ttu-id="195e7-281">Als u de bestanden niet vrijgeeft of verwijdert, worden ze verwijderd nadat de standaardbewaartermijn voor quarantaine is verstreken.</span><span class="sxs-lookup"><span data-stu-id="195e7-281">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="195e7-282">Acties op meerdere in quarantaine geplaatste bestanden</span><span class="sxs-lookup"><span data-stu-id="195e7-282">Actions on multiple quarantined files</span></span>

<span data-ttu-id="195e7-283">Wanneer u meerdere in quarantaine geplaatste bestanden in de lijst selecteert (maximaal 100), wordt het flyoutvenster **bulkacties** weergegeven waar u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="195e7-283">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="195e7-284">**Bestanden vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="195e7-284">**Release files**</span></span>

- <span data-ttu-id="195e7-285">**Bestanden verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="195e7-285">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="195e7-286">Als u een werk- of schoolaccount gebruikt met algemene beheerdersbevoegdheden (of de juiste functies van het Beveiligingscentrum & Compliance Center) in uw organisatie, u zich aanmelden en [naar het Security & Compliance Center gaan.](../../compliance/go-to-the-securitycompliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="195e7-286">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="195e7-287">Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren</span><span class="sxs-lookup"><span data-stu-id="195e7-287">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="195e7-288">De cmdlets die u gebruikt om berichten en bestanden in quarantaine weer te geven en te beheren, zijn:</span><span class="sxs-lookup"><span data-stu-id="195e7-288">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="195e7-289">Bericht verwijderen-quarantaine</span><span class="sxs-lookup"><span data-stu-id="195e7-289">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="195e7-290">Bericht exporteren-quarantaine</span><span class="sxs-lookup"><span data-stu-id="195e7-290">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="195e7-291">Bericht in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="195e7-291">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="195e7-292">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)Houd er rekening mee dat deze cmdlet alleen is voor berichten, geen malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.</span><span class="sxs-lookup"><span data-stu-id="195e7-292">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="195e7-293">Bericht release-quarantaine</span><span class="sxs-lookup"><span data-stu-id="195e7-293">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
