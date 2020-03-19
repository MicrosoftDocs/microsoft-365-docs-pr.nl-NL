---
title: Berichten en bestanden in quarantaine beheren als beheerder in Office 365
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
description: Beheerders kunnen alle typen berichten in quarantaine voor alle gebruikers bekijken, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor de stroom (transportregels).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857071"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="93ae1-104">Berichten en bestanden in quarantaine beheren als beheerder in Office 365</span><span class="sxs-lookup"><span data-stu-id="93ae1-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="93ae1-105">Quarantaine bevat mogelijk gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="93ae1-106">Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="93ae1-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="93ae1-107">Beheerders kunnen alle typen berichten in quarantaine voor alle gebruikers bekijken, vrijgeven en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="93ae1-108">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor de mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="93ae1-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="93ae1-109">Beheerders kunnen ook valse positieven melden aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93ae1-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="93ae1-110">Beheerders in organisaties met Office 365 Advance Threat Protection (ATP) kunnen ook in quarantaine geplaatste bestanden bekijken, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93ae1-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="93ae1-111">U bekijkt en beheert berichten in quarantaine in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Office 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="93ae1-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="93ae1-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="93ae1-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="93ae1-113">Als u het Office 365 Security <https://protection.office.com>& Compliance Center wilt openen, gaat u naar .</span><span class="sxs-lookup"><span data-stu-id="93ae1-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="93ae1-114">Als u de quarantainepagina <https://protection.office.com/quarantine>rechtstreeks wilt openen, gaat u naar .</span><span class="sxs-lookup"><span data-stu-id="93ae1-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="93ae1-115">Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ae1-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="93ae1-116">Zie Verbinding maken met [PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor de beveiliging van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93ae1-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="93ae1-117">U moet machtigingen toegewezen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de **quarantainerol** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="93ae1-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="93ae1-118">Deze rol wordt standaard toegewezen aan de rolgroepen **Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="93ae1-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="93ae1-119">Zie [Machtigingen in het Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="93ae1-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="93ae1-120">Berichten in quarantaine worden standaard bewaard voordat ze automatisch worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="93ae1-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="93ae1-121">Berichten in quarantaine geplaatst door antispambeleid (spam, phishing en bulke-mail): 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="93ae1-122">Dit is de standaard waarde en maximale waarde.</span><span class="sxs-lookup"><span data-stu-id="93ae1-122">This is the default and maximum value.</span></span> <span data-ttu-id="93ae1-123">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="93ae1-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="93ae1-124">Berichten die in quarantaine worden geplaatst door regels voor e-mailstroom (de regelactie is Het bericht verzenden **naar de gehoste quarantaine):** 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="93ae1-125">Je deze waarde niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-125">You can't change this value.</span></span>

  - <span data-ttu-id="93ae1-126">Berichten die malware bevatten: 15 dagen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="93ae1-127">Wanneer een bericht uit quarantaine verloopt, u het niet herstellen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="93ae1-128">Het Security & Compliance Center gebruiken om e-mailberichten in quarantaine te beheren</span><span class="sxs-lookup"><span data-stu-id="93ae1-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="93ae1-129">In quarantaine geplaatste e-mail weergeven</span><span class="sxs-lookup"><span data-stu-id="93ae1-129">View quarantined email</span></span>

1. <span data-ttu-id="93ae1-130">Ga in het Security and Compliance Center naar **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="93ae1-131">Controleer of **Weergave in quarantaine** is ingesteld op **e-mail**met standaardwaarde .</span><span class="sxs-lookup"><span data-stu-id="93ae1-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="93ae1-132">U de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="93ae1-133">Klik op **Kolommen wijzigen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="93ae1-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="93ae1-134">De standaardwaarden zijn gemarkeerd met<sup>\*</sup>een sterretje ( ):</span><span class="sxs-lookup"><span data-stu-id="93ae1-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="93ae1-135">**Ontvangen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-136">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-137">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-138">**Quarantaine reden**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-139">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-140">**Beleidstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-141">**Verloopt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-142">**Ontvanger**</span><span class="sxs-lookup"><span data-stu-id="93ae1-142">**Recipient**</span></span>

   - <span data-ttu-id="93ae1-143">**Bericht-id**</span><span class="sxs-lookup"><span data-stu-id="93ae1-143">**Message ID**</span></span>

   - <span data-ttu-id="93ae1-144">**Beleidsnaam**</span><span class="sxs-lookup"><span data-stu-id="93ae1-144">**Policy name**</span></span>

   - <span data-ttu-id="93ae1-145">**Grootte**</span><span class="sxs-lookup"><span data-stu-id="93ae1-145">**Size**</span></span>

   - <span data-ttu-id="93ae1-146">**Richting**</span><span class="sxs-lookup"><span data-stu-id="93ae1-146">**Direction**</span></span>

   <span data-ttu-id="93ae1-147">Wanneer u klaar bent, klikt u op **Opslaan**of klikt u op **Instellen op standaard**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="93ae1-148">Als u de resultaten wilt filteren, klikt u op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="93ae1-149">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="93ae1-149">The available filters are:</span></span>

   - <span data-ttu-id="93ae1-150">**Verlooptijd**: Filter berichten op het moment dat ze verlopen vanuit quarantaine:</span><span class="sxs-lookup"><span data-stu-id="93ae1-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="93ae1-151">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="93ae1-151">**Today**</span></span>

     - <span data-ttu-id="93ae1-152">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-152">**Next 2 days**</span></span>

     - <span data-ttu-id="93ae1-153">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-153">**Next 7 days**</span></span>

     - <span data-ttu-id="93ae1-154">**Aangepast:** voer een **begindatum** en **einddatum**in .</span><span class="sxs-lookup"><span data-stu-id="93ae1-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="93ae1-155">**Ontvangen tijd**: Voer een **begindatum** en **einddatum**in .</span><span class="sxs-lookup"><span data-stu-id="93ae1-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="93ae1-156">**Quarantaine reden**:</span><span class="sxs-lookup"><span data-stu-id="93ae1-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="93ae1-157">**Beleid**: Het bericht kwam overeen met de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="93ae1-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="93ae1-158">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="93ae1-158">**Bulk**</span></span>

     - <span data-ttu-id="93ae1-159">**Phish**</span><span class="sxs-lookup"><span data-stu-id="93ae1-159">**Phish**</span></span>

     - <span data-ttu-id="93ae1-160">**Malware**</span><span class="sxs-lookup"><span data-stu-id="93ae1-160">**Malware**</span></span>

     - <span data-ttu-id="93ae1-161">**Spam**</span><span class="sxs-lookup"><span data-stu-id="93ae1-161">**Spam**</span></span>

     - <span data-ttu-id="93ae1-162">**Hoog vertrouwen Phish**</span><span class="sxs-lookup"><span data-stu-id="93ae1-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="93ae1-163">**E-mailontvanger:** alle gebruikers of alleen berichten die naar u zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="93ae1-164">Eindgebruikers kunnen alleen berichten in quarantaine beheren die naar hen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="93ae1-165">Als u het filter wilt wissen, klikt u op **Wissen**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="93ae1-166">Als u de filterflyout wilt verbergen, klikt u nogmaals op **Filter.**</span><span class="sxs-lookup"><span data-stu-id="93ae1-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="93ae1-167">**Gebruik Sorteerresultaten op** (standaard de knop **Bericht-id)** en een bijbehorende waarde om specifieke berichten te vinden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="93ae1-168">Wildcards worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="93ae1-168">Wildcards aren't supported.</span></span> <span data-ttu-id="93ae1-169">U zoeken op de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="93ae1-169">You can search by the following values:</span></span>

   - <span data-ttu-id="93ae1-170">**Bericht-id:** de wereldwijd unieke id van het bericht.</span><span class="sxs-lookup"><span data-stu-id="93ae1-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="93ae1-171">U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u vaststelt dat het bericht in quarantaine is geplaatst in plaats van bezorgd.</span><span class="sxs-lookup"><span data-stu-id="93ae1-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="93ae1-172">Zorg ervoor dat u de volledige waarde van de\<\>bericht-id opneemt, waaronder hoekhaakjes ( ).</span><span class="sxs-lookup"><span data-stu-id="93ae1-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="93ae1-173">Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="93ae1-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="93ae1-174">**Afzender e-mailadres:** Het e-mailadres van één afzender.</span><span class="sxs-lookup"><span data-stu-id="93ae1-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="93ae1-175">**E-mailadres van**de ontvanger: het e-mailadres van één ontvanger.</span><span class="sxs-lookup"><span data-stu-id="93ae1-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="93ae1-176">**Onderwerp**: Gebruik het hele onderwerp van het bericht.</span><span class="sxs-lookup"><span data-stu-id="93ae1-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="93ae1-177">De zoekopdracht is niet hoofdlettergevoelig.</span><span class="sxs-lookup"><span data-stu-id="93ae1-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="93ae1-178">Nadat u de zoekcriteria hebt ![ingevoerd, klikt u op Knop](../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="93ae1-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="93ae1-179">Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om details hierover weer te geven en u er actie op ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="93ae1-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="93ae1-180">Berichtresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="93ae1-180">Export message results</span></span>

1. <span data-ttu-id="93ae1-181">Selecteer de berichten waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="93ae1-182">Klik op **Ja** in het bevestigingsbericht waarin u wordt gewaarschuwd het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="93ae1-183">Wanneer uw export klaar is, u de downloadlocatie voor het CSV-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="93ae1-184">Berichtgegevens in quarantaine weergeven</span><span class="sxs-lookup"><span data-stu-id="93ae1-184">View quarantined message details</span></span>

<span data-ttu-id="93ae1-185">Wanneer u een e-mailbericht in de lijst selecteert, worden de volgende berichtgegevens weergegeven in het flyout-venster **Details:**</span><span class="sxs-lookup"><span data-stu-id="93ae1-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="93ae1-186">**Bericht-id:** de wereldwijd unieke id voor het bericht.</span><span class="sxs-lookup"><span data-stu-id="93ae1-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="93ae1-187">**Afzenderadres**</span><span class="sxs-lookup"><span data-stu-id="93ae1-187">**Sender address**</span></span>

- <span data-ttu-id="93ae1-188">**Ontvangen**: De datum/tijd waarop het bericht is ontvangen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="93ae1-189">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="93ae1-189">**Subject**</span></span>

- <span data-ttu-id="93ae1-190">**Quarantaine reden**: Geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeen met een e-mailstroom regel **(Transport regel),** of werd geïdentificeerd als **malware**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="93ae1-191">**Ontvangers:** als het bericht meerdere geadresseerden bevat, moet u op **Bericht voorbeeld** of **berichtkop weergeven** klikken om de volledige lijst met geadresseerden weer te geven.</span><span class="sxs-lookup"><span data-stu-id="93ae1-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="93ae1-192">**Verloopt:** De datum/tijd waarop het bericht automatisch en permanent uit quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="93ae1-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="93ae1-193">**Vrijgegeven aan**: Alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="93ae1-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="93ae1-194">**Nog niet vrijgegeven aan**: Alle e-mailadressen (indien aanwezig) waarop het bericht nog niet is vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="93ae1-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="93ae1-195">Actie ondernemen op e-mail in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-195">Take action on quarantined email</span></span>

<span data-ttu-id="93ae1-196">Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in het flyout-venster **Details:**</span><span class="sxs-lookup"><span data-stu-id="93ae1-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="93ae1-197">**Bericht vrijgeven:** kies in het flyoutdeelvenster dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="93ae1-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="93ae1-198">**Berichten rapporteren aan Microsoft voor analyse**: dit is standaard geselecteerd en rapporteert het ten onrechte geplaatste bericht aan Microsoft als een vals-positief.</span><span class="sxs-lookup"><span data-stu-id="93ae1-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="93ae1-199">Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="93ae1-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="93ae1-200">Afhankelijk van hun analyse kunnen de regels voor spamfilter voor de hele service worden aangepast om het bericht door te laten.</span><span class="sxs-lookup"><span data-stu-id="93ae1-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="93ae1-201">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="93ae1-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="93ae1-202">**Berichten vrijgeven aan alle ontvangers**</span><span class="sxs-lookup"><span data-stu-id="93ae1-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="93ae1-203">**Berichten vrijgeven aan specifieke ontvangers**</span><span class="sxs-lookup"><span data-stu-id="93ae1-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="93ae1-204">**Berichten vrijgeven aan andere mensen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-204">**Release messages to other people**</span></span>

  <span data-ttu-id="93ae1-205">Klik op **Berichten vrijgeven**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="93ae1-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="93ae1-206">Opmerkingen over het vrijgeven van berichten:</span><span class="sxs-lookup"><span data-stu-id="93ae1-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="93ae1-207">U een bericht niet meerdere dan één keer vrijgeven aan dezelfde ontvanger.</span><span class="sxs-lookup"><span data-stu-id="93ae1-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="93ae1-208">Alleen ontvangers die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële ontvangers.</span><span class="sxs-lookup"><span data-stu-id="93ae1-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="93ae1-209">**Berichtkoptekst weergeven:** kies deze koppeling om de tekst van de berichtkoptekst te bekijken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="93ae1-210">Als u de koptekstvelden en -waarden in de diepte wilt analyseren, kopieert u de tekst van de koptekst van het bericht naar uw klembord en kiest u **Vervolgens Microsoft Message Header Analyzer** om naar de Externe verbindingsanalyse te gaan (klik met de rechtermuisknop en kies Openen op een nieuw **tabblad** als u Office 365 niet wilt verlaten om deze taak te voltooien).</span><span class="sxs-lookup"><span data-stu-id="93ae1-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="93ae1-211">Plak de berichtkoptekst op de pagina in de sectie Message Header Analyzer en kies **Kopteksten analyseren:**</span><span class="sxs-lookup"><span data-stu-id="93ae1-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="93ae1-212">**Voorbeeldbericht:** Kies in het flyoutdeelvenster dat wordt weergegeven een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="93ae1-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="93ae1-213">**Bronweergave**: Toont de HTML-versie van de berichttekst met alle koppelingen uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="93ae1-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="93ae1-214">**Tekstweergave**: Toont de berichttekst in platte tekst.</span><span class="sxs-lookup"><span data-stu-id="93ae1-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="93ae1-215">**Verwijderen uit quarantaine**: Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder dat het naar de oorspronkelijke geadresseerden is verzonden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="93ae1-216">**Downloadbericht**: Selecteer in het flyoutvenster dat wordt weergegeven **de risico's van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.</span><span class="sxs-lookup"><span data-stu-id="93ae1-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="93ae1-217">**Bericht verzenden:** kies in het flyoutdeelvenster dat wordt weergegeven de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="93ae1-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="93ae1-218">**Objecttype**: **E-mail** (standaard), **URL**of **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="93ae1-219">**Inzendingsindeling**: **Netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand).</span><span class="sxs-lookup"><span data-stu-id="93ae1-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="93ae1-220">Houd er rekening mee dat als u **Bestand** selecteert en vervolgens **Netwerkbericht-id**selecteert, de oorspronkelijke waarde is verdwenen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="93ae1-221">**Geadresseerden**: Typ bij lease één oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle geadresseerden te identificeren.</span><span class="sxs-lookup"><span data-stu-id="93ae1-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="93ae1-222">U ook op **Alles selecteren** klikken en vervolgens selectief afzonderlijke ontvangers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="93ae1-223">**Reden voor indiening**: **Had niet geblokkeerd moeten zijn** (standaard) of had geblokkeerd moeten **worden.**</span><span class="sxs-lookup"><span data-stu-id="93ae1-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="93ae1-224">Als u klaar bent, klikt u op **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="93ae1-225">Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaardbewaarringsperiode voor quarantaine is verstreken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="93ae1-226">Actie ondernemen op meerdere e-mailberichten in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="93ae1-227">Wanneer u meerdere berichten in quarantaine selecteert in de lijst (maximaal 100), wordt het flyout-venster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="93ae1-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="93ae1-228">**Berichten vrijgeven:** de opties zijn hetzelfde als wanneer u één bericht uitbrengt, behalve dat u Berichten vrijgeven **aan specifieke ontvangers**niet selecteren; u alleen **Bericht vrijgeven aan alle ontvangers** selecteren of Berichten vrijgeven aan andere **mensen.**</span><span class="sxs-lookup"><span data-stu-id="93ae1-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="93ae1-229">**Berichten verwijderen:** Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="93ae1-230">Als u klaar bent, klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="93ae1-231">Alleen ATP: gebruik het Security & Compliance Center om in quarantaine geplaatste bestanden te beheren</span><span class="sxs-lookup"><span data-stu-id="93ae1-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="93ae1-232">De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor ATP-abonnement 1- en Plan 2-abonnees.</span><span class="sxs-lookup"><span data-stu-id="93ae1-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="93ae1-233">In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="93ae1-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="93ae1-234">In quarantaine geplaatste bestanden weergeven</span><span class="sxs-lookup"><span data-stu-id="93ae1-234">View quarantined files</span></span>

1. <span data-ttu-id="93ae1-235">Ga in het Security and Compliance Center naar **Threat Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="93ae1-236">**Weergave in quarantaine** wijzigen in de standaardwaardebestanden . **files**</span><span class="sxs-lookup"><span data-stu-id="93ae1-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="93ae1-237">U sorteren op een veld door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="93ae1-238">U de resultaten sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="93ae1-239">Klik op **Kolommen wijzigen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="93ae1-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="93ae1-240">De standaardkolommen zijn gemarkeerd met<sup>\*</sup>een sterretje ( ):</span><span class="sxs-lookup"><span data-stu-id="93ae1-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="93ae1-241">**Gebruiker**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-242">**Locatie**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-243">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-244">**Bestands-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-245">**Bestandsgrootte**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-246">**Verloopt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-247">**Vrijgegeven?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93ae1-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="93ae1-248">**Gedetecteerd door**</span><span class="sxs-lookup"><span data-stu-id="93ae1-248">**Detected by**</span></span>

   - <span data-ttu-id="93ae1-249">**Gewijzigd op tijd**</span><span class="sxs-lookup"><span data-stu-id="93ae1-249">**Modified by time**</span></span>

4. <span data-ttu-id="93ae1-250">Als u de resultaten wilt filteren, klikt u op **Filter**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="93ae1-251">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="93ae1-251">The available filters are:</span></span>

   - <span data-ttu-id="93ae1-252">**Verlooptijd**: Filter berichten op het moment dat ze verlopen vanuit quarantaine:</span><span class="sxs-lookup"><span data-stu-id="93ae1-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="93ae1-253">**Vandaag**</span><span class="sxs-lookup"><span data-stu-id="93ae1-253">**Today**</span></span>

     - <span data-ttu-id="93ae1-254">**Komende 2 dagen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-254">**Next 2 days**</span></span>

     - <span data-ttu-id="93ae1-255">**Komende 7 dagen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-255">**Next 7 days**</span></span>

     - <span data-ttu-id="93ae1-256">Een aangepast datum-/tijdsbereik.</span><span class="sxs-lookup"><span data-stu-id="93ae1-256">A custom date/time range.</span></span>

   - <span data-ttu-id="93ae1-257">**Ontvangen tijd**</span><span class="sxs-lookup"><span data-stu-id="93ae1-257">**Received time**</span></span>

   - <span data-ttu-id="93ae1-258">**Quarantaine reden:** De enige beschikbare waarde is **Malware**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="93ae1-259">Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om details hierover weer te geven en u er actie op ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).</span><span class="sxs-lookup"><span data-stu-id="93ae1-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="93ae1-260">Bestandsresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="93ae1-260">Export file results</span></span>

1. <span data-ttu-id="93ae1-261">Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="93ae1-262">Klik op **Ja** in het bevestigingsbericht waarin u wordt gewaarschuwd het browservenster open te houden.</span><span class="sxs-lookup"><span data-stu-id="93ae1-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="93ae1-263">Wanneer uw export klaar is, u de downloadlocatie voor het CSV-bestand benoemen en kiezen.</span><span class="sxs-lookup"><span data-stu-id="93ae1-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="93ae1-264">In quarantaine geplaatste bestandsgegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="93ae1-264">View quarantined file details</span></span>

<span data-ttu-id="93ae1-265">Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsgegevens weergegeven in het flyout-venster **Details:**</span><span class="sxs-lookup"><span data-stu-id="93ae1-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="93ae1-266">**Bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="93ae1-266">**File Name**</span></span>

- <span data-ttu-id="93ae1-267">**Bestands-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="93ae1-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="93ae1-268">**Schadelijke inhoud gedetecteerd op** De datum/tijd dat het bestand in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="93ae1-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="93ae1-269">**Verloopt:** de datum waarop het bestand uit quarantaine wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="93ae1-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="93ae1-270">**Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.</span><span class="sxs-lookup"><span data-stu-id="93ae1-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="93ae1-271">**Vrijgegeven?**</span><span class="sxs-lookup"><span data-stu-id="93ae1-271">**Released?**</span></span>

- <span data-ttu-id="93ae1-272">**Malwarenaam**</span><span class="sxs-lookup"><span data-stu-id="93ae1-272">**Malware Name**</span></span>

- <span data-ttu-id="93ae1-273">**Document-ID:** een unieke id voor het document.</span><span class="sxs-lookup"><span data-stu-id="93ae1-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="93ae1-274">**Bestandsgrootte**: In kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="93ae1-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="93ae1-275">**Organisatie** De unieke ID van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93ae1-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="93ae1-276">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="93ae1-276">**Last modified**</span></span>

- <span data-ttu-id="93ae1-277">**Gewijzigd door**: De gebruiker die het bestand het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="93ae1-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="93ae1-278">**Secure Hash Algorithm 256-bit (SHA-256) waarde**: U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="93ae1-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="93ae1-279">Actie ondernemen op bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-279">Take action on quarantined files</span></span>

<span data-ttu-id="93ae1-280">Wanneer u een bestand in de lijst selecteert, u de volgende acties uitvoeren in het bestand in het flyout-venster **Details:**</span><span class="sxs-lookup"><span data-stu-id="93ae1-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="93ae1-281">**Bestanden vrijgeven:** Selecteer (standaard) of selecteer **Rapportbestanden aan Microsoft voor analyse**en klik vervolgens op Bestanden **vrijgeven**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="93ae1-282">**Downloadbestand**</span><span class="sxs-lookup"><span data-stu-id="93ae1-282">**Download file**</span></span>

- <span data-ttu-id="93ae1-283">**Bestand uit quarantaine verwijderen**</span><span class="sxs-lookup"><span data-stu-id="93ae1-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="93ae1-284">Als u de bestanden niet vrijgeeft of verwijdert, worden ze verwijderd nadat de standaardbewaarringsperiode voor quarantaine is verstreken.</span><span class="sxs-lookup"><span data-stu-id="93ae1-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="93ae1-285">Acties op meerdere bestanden in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="93ae1-286">Wanneer u meerdere in quarantaine geplaatste bestanden in de lijst selecteert (maximaal 100), wordt het flyout-venster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="93ae1-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="93ae1-287">**Bestanden vrijgeven**</span><span class="sxs-lookup"><span data-stu-id="93ae1-287">**Release files**</span></span>

- <span data-ttu-id="93ae1-288">**Bestanden verwijderen:** Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, worden de bestanden onmiddellijk verwijderd.</span><span class="sxs-lookup"><span data-stu-id="93ae1-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="93ae1-289">Als u klaar bent, klikt u op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="93ae1-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="93ae1-290">Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell gebruiken om berichten en bestanden in quarantaine te bekijken en te beheren</span><span class="sxs-lookup"><span data-stu-id="93ae1-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="93ae1-291">De cmdlets die u gebruikt om berichten en bestanden in quarantaine te bekijken en te beheren zijn:</span><span class="sxs-lookup"><span data-stu-id="93ae1-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="93ae1-292">Bericht verwijderen in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="93ae1-293">Bericht exporteren-quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="93ae1-294">Bericht in quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="93ae1-295">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)Houd er rekening mee dat deze cmdlet alleen voor berichten is, niet voor malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.</span><span class="sxs-lookup"><span data-stu-id="93ae1-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="93ae1-296">Bericht in de release-quarantaine</span><span class="sxs-lookup"><span data-stu-id="93ae1-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
