---
title: Beheerdersinzendingen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze de portal Inzendingen in het Microsoft 365-beveiligingscentrum kunnen gebruiken om verdachte e-mailberichten, vermoedelijke phishingmails, spam en andere potentieel schadelijke berichten, URL's en e-mailbijlagen bij Microsoft in te dienen voor het opnieuw controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878686"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="66357-103">Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden</span><span class="sxs-lookup"><span data-stu-id="66357-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="66357-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="66357-104">**Applies to**</span></span>
- [<span data-ttu-id="66357-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="66357-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="66357-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="66357-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="66357-107">In Microsoft 365 organisaties met postvakken in Exchange Online kunnen beheerders de portal Inzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.</span><span class="sxs-lookup"><span data-stu-id="66357-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="66357-108">Wanneer u een e-mailbericht indient, krijgt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="66357-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="66357-109">**Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="66357-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="66357-110">**Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.</span><span class="sxs-lookup"><span data-stu-id="66357-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="66357-111">**Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="66357-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="66357-112">**Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="66357-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66357-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span><span class="sxs-lookup"><span data-stu-id="66357-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="66357-114">Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="66357-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="66357-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="66357-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="66357-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="66357-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="66357-117">U opent het Microsoft 365 beveiligingscentrum op <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="66357-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="66357-118">Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="66357-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="66357-119">Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="66357-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="66357-120">**Organisatiebeheer** of **Beveiligingslezer** in het [Microsoft 365 beveiligingscentrum.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="66357-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="66357-121">**Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="66357-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="66357-122">Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-the-custom-mailbox) weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="66357-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="66357-123">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="66357-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="66357-124">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="66357-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="66357-125">Ga in [Microsoft 365 beveiligingscentrum](../defender/overview-security-center.md)naar **Inzendingen** en controleer of  u zich op het tabblad Ingediend voor analyse hebt en klik vervolgens op Verzenden bij **Microsoft voor controle.**</span><span class="sxs-lookup"><span data-stu-id="66357-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="66357-126">Gebruik de **flyout Verzenden bij Microsoft** voor controle die wordt weergegeven om het bericht, de URL of de e-mailbijlage in te dienen, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="66357-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="66357-127">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="66357-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="66357-128">Selecteer **e-mail** in de sectie Selecteer het **inzendingstype.**</span><span class="sxs-lookup"><span data-stu-id="66357-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="66357-129">Gebruik een van de volgende opties in de sectie **Netwerkbericht-id toevoegen** of het e-mailbestand uploaden:</span><span class="sxs-lookup"><span data-stu-id="66357-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="66357-130">**De** e-mailnetwerkbericht-id toevoegen: dit is een GUID-waarde die beschikbaar is in de koptekst **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="66357-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="66357-131">**Upload het e-mailbestand:** Klik **op Bestanden bladeren.**</span><span class="sxs-lookup"><span data-stu-id="66357-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="66357-132">Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="66357-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66357-133">De mogelijkheid om berichten zo oud als 30 dagen in te dienen, is tijdelijk opgeschort voor Defender voor Office 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="66357-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="66357-134">Beheerders kunnen slechts 7 dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="66357-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="66357-135">Geef in **de sectie Kies een geadresseerde** met een probleem de geadresseerde op tegen wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="66357-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="66357-136">Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="66357-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="66357-137">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="66357-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="66357-138">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="66357-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66357-139">**Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="66357-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="66357-140">Als u het niet zeker weet, gebruikt u uw beste beoordeling.</span><span class="sxs-lookup"><span data-stu-id="66357-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="66357-141">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="66357-141">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van nieuwe URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="66357-143">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="66357-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="66357-144">Selecteer URL **in de sectie Selecteer** het inzendingstype. </span><span class="sxs-lookup"><span data-stu-id="66357-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="66357-145">Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="66357-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="66357-146">Selecteer in **de sectie** Reden voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="66357-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="66357-147">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="66357-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66357-148">**Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="66357-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="66357-149">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="66357-149">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van nieuwe e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="66357-151">Een verdachte e-mailbijlage indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="66357-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="66357-152">Selecteer in **de sectie Selecteer het inzendingstype** de optie **E-mailbijlage**.</span><span class="sxs-lookup"><span data-stu-id="66357-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="66357-153">Klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="66357-153">Click **Choose File**.</span></span> <span data-ttu-id="66357-154">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="66357-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="66357-155">Selecteer in **de sectie** Reden voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="66357-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="66357-156">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="66357-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="66357-157">**Moet zijn geblokkeerd:** **Malware** is de enige keuze en wordt automatisch geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="66357-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="66357-158">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="66357-158">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van nieuwe bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="66357-160">Items weergeven die zijn ingediend voor analyse</span><span class="sxs-lookup"><span data-stu-id="66357-160">View items Submitted for analysis</span></span>

<span data-ttu-id="66357-161">Ga in Microsoft 365 beveiligingscentrum naar **Inzendingen** en controleer of u zich op het tabblad **Ingediend voor analyse** hebt</span><span class="sxs-lookup"><span data-stu-id="66357-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="66357-162">Op de opdrachtbalk in het midden van de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Indienings-id **(een** GUID-waarde die aan elke inzending is toegewezen) door een waarde in het vak in te voeren en op Knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="66357-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66357-163">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="66357-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66357-164">Als u de filtercriteria wilt wijzigen, klikt u op de **knop Filter** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="66357-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="66357-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="66357-165">**Sender**</span></span>
- <span data-ttu-id="66357-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="66357-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="66357-167">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="66357-167">**Submitted by**</span></span>
- <span data-ttu-id="66357-168">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-168">**Submission type**</span></span>
- <span data-ttu-id="66357-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="66357-169">**Status**</span></span>

![Nieuwe filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="66357-171">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="66357-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66357-172">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="66357-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="66357-173">Onder de grafiek ziet u drie tabbladen: **E-mail** (standaard), **URL** en **E-mailbijlage.**</span><span class="sxs-lookup"><span data-stu-id="66357-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="66357-174">E-mailberichten van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="66357-174">View admin email submissions</span></span>

<span data-ttu-id="66357-175">U kunt onder aan de pagina op de knop **Kolommen** aanpassen klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="66357-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66357-176">**Datum**</span><span class="sxs-lookup"><span data-stu-id="66357-176">**Date**</span></span>
- <span data-ttu-id="66357-177">**Inzending-id:** een GUID-waarde die aan elke inzending is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="66357-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="66357-178">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-179">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-180">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="66357-180">**Sender**</span></span>
- <span data-ttu-id="66357-181">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-182">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-182">**Submission type**</span></span>
- <span data-ttu-id="66357-183">**Bezorgingsreden**</span><span class="sxs-lookup"><span data-stu-id="66357-183">**Delivery reason**</span></span>
- <span data-ttu-id="66357-184">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66357-185"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="66357-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="66357-186">Details van de inzending van beheerders opnieuw scannen</span><span class="sxs-lookup"><span data-stu-id="66357-186">Admin submission rescan details</span></span>

<span data-ttu-id="66357-187">Berichten die worden verzonden in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de flyout met inzendingendetails:</span><span class="sxs-lookup"><span data-stu-id="66357-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="66357-188">Of er tijdens de levering een fout zat in de e-mailverificatie van de afzender.</span><span class="sxs-lookup"><span data-stu-id="66357-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="66357-189">Informatie over eventuele beleidstreffers die het oordeel over een bericht kunnen hebben beïnvloed of overschreven.</span><span class="sxs-lookup"><span data-stu-id="66357-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="66357-190">Huidige deactiveringsresultaten om te zien of de URL's of bestanden in het bericht schadelijk waren of niet.</span><span class="sxs-lookup"><span data-stu-id="66357-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="66357-191">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="66357-191">Feedback from graders.</span></span>

<span data-ttu-id="66357-192">Als een overschrijving is gevonden, zou het opnieuw scannen in enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="66357-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="66357-193">Als er geen probleem was bij e-mailverificatie of bezorging werd niet beïnvloed door een overschrijven, kan de feedback van cijferaars maximaal een dag duren.</span><span class="sxs-lookup"><span data-stu-id="66357-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="66357-194">URL-inzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="66357-194">View admin URL submissions</span></span>

<span data-ttu-id="66357-195">Klik op **het tabblad URL.**</span><span class="sxs-lookup"><span data-stu-id="66357-195">Click the **URL** tab.</span></span>

<span data-ttu-id="66357-196">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="66357-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66357-197">**Datum**</span><span class="sxs-lookup"><span data-stu-id="66357-197">**Date**</span></span>
- <span data-ttu-id="66357-198">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="66357-198">**Submission ID**</span></span>
- <span data-ttu-id="66357-199">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-201">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-201">**Submission type**</span></span>
- <span data-ttu-id="66357-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66357-203"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="66357-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="66357-204">E-mailbijlage-inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="66357-204">View email attachment submissions</span></span>

<span data-ttu-id="66357-205">Klik op **het tabblad** Bijlagen.</span><span class="sxs-lookup"><span data-stu-id="66357-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="66357-206">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="66357-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66357-207">**Datum**</span><span class="sxs-lookup"><span data-stu-id="66357-207">**Date**</span></span>
- <span data-ttu-id="66357-208">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="66357-208">**Submission ID**</span></span>
- <span data-ttu-id="66357-209">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-210">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-211">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-211">**Submission type**</span></span>
- <span data-ttu-id="66357-212">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="66357-213"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="66357-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="66357-214">Gebruikersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="66357-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="66357-215">Als u de invoeging Rapportbericht , de [invoeging](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)melden of personen de ingebouwde rapportage [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)op internet hebben  geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Gebruikersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="66357-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="66357-216">Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="66357-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="66357-217">Selecteer het **tabblad Gebruikersinzendingen** en klik vervolgens op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="66357-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="66357-218">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="66357-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66357-219">**Verzonden op**</span><span class="sxs-lookup"><span data-stu-id="66357-219">**Submitted on**</span></span>
- <span data-ttu-id="66357-220">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-221">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-222">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="66357-222">**Sender**</span></span>
- <span data-ttu-id="66357-223">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-224">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-224">**Submission type**</span></span>

<span data-ttu-id="66357-225"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="66357-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="66357-226">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Afzender door een waarde in het vak in te voeren en op knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="66357-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66357-227">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="66357-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66357-228">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="66357-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="66357-229">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="66357-229">**Sender domain**</span></span>
- <span data-ttu-id="66357-230">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="66357-230">**Subject**</span></span>
- <span data-ttu-id="66357-231">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="66357-231">**Submitted by**</span></span>
- <span data-ttu-id="66357-232">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-232">**Submission type**</span></span>
- <span data-ttu-id="66357-233">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="66357-233">**Sender IP**</span></span>

![Nieuwe filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="66357-235">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="66357-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66357-236">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="66357-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="66357-237">Gebruikersinzendingen weergeven in het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="66357-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="66357-238">**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, kunt u berichten bekijken en verzenden die zijn bezorgd in het rapportpostvak.</span><span class="sxs-lookup"><span data-stu-id="66357-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="66357-239">Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="66357-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="66357-240">Selecteer het **tabblad Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="66357-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="66357-241">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="66357-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="66357-242">**Verzonden op**</span><span class="sxs-lookup"><span data-stu-id="66357-242">**Submitted on**</span></span>
- <span data-ttu-id="66357-243">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-244">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-245">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="66357-245">**Sender**</span></span>
- <span data-ttu-id="66357-246">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66357-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="66357-247">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="66357-247">**Submission type**</span></span>

<span data-ttu-id="66357-248">Boven aan de pagina kunt u een begindatum, een einddatum  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op knop ![ Vernieuwen te ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="66357-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="66357-249">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="66357-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="66357-250">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="66357-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="66357-251">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="66357-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="66357-252">Als organisaties zijn geconfigureerd om alleen naar een aangepast postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in de portal Gebruikers gerapporteerde berichten altijd leeg.</span><span class="sxs-lookup"><span data-stu-id="66357-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="66357-253">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="66357-253">Undo user submissions</span></span>

<span data-ttu-id="66357-254">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="66357-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="66357-255">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="66357-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="66357-256">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="66357-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="66357-257">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="66357-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="66357-258">Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.</span><span class="sxs-lookup"><span data-stu-id="66357-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="66357-259">Selecteer op **het tabblad Gerapporteerde** berichten van gebruiker  een bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="66357-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="66357-260">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="66357-260">**Report clean**</span></span>
- <span data-ttu-id="66357-261">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="66357-261">**Report phishing**</span></span>
- <span data-ttu-id="66357-262">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="66357-262">**Report malware**</span></span>
- <span data-ttu-id="66357-263">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="66357-263">**Report spam**</span></span>

![Nieuwe opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
