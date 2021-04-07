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
description: Beheerders kunnen leren hoe ze de portal Inzendingen in het beveiligings- & compliancecentrum kunnen gebruiken om verdachte e-mailberichten, vermoedelijke phishingmails, spam en andere potentieel schadelijke berichten, URL's en bestanden naar Microsoft te verzenden voor scannen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0975d5b6c2d29c94a30f7bbc703221b80217761
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599873"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b903e-103">Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden</span><span class="sxs-lookup"><span data-stu-id="b903e-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b903e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b903e-104">**Applies to**</span></span>
- [<span data-ttu-id="b903e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b903e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b903e-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b903e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="b903e-107">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Inzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.</span><span class="sxs-lookup"><span data-stu-id="b903e-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b903e-108">Wanneer u een e-mailbericht indient, krijgt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="b903e-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="b903e-109">**Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="b903e-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="b903e-110">**Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.</span><span class="sxs-lookup"><span data-stu-id="b903e-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="b903e-111">**Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="b903e-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="b903e-112">**Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="b903e-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b903e-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span><span class="sxs-lookup"><span data-stu-id="b903e-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="b903e-114">Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="b903e-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="b903e-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b903e-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b903e-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b903e-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b903e-117">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b903e-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b903e-118">Als u rechtstreeks naar de pagina **Inzending** wilt gaan, gebruikt <https://protection.office.com/reportsubmission> u .</span><span class="sxs-lookup"><span data-stu-id="b903e-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b903e-119">Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="b903e-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b903e-120">**Organisatiebeheer** of **Beveiligingslezer** in het [beveiligings- & compliancecentrum.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="b903e-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="b903e-121">**Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="b903e-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="b903e-122">Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-the-custom-mailbox) weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="b903e-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="b903e-123">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="b903e-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="b903e-124">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="b903e-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="b903e-125">Ga in het & Compliancecentrum naar Threat **management** \> **Submissions,** controleer of  u zich op het tabblad Beheerdersinzendingen en klik vervolgens op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="b903e-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="b903e-126">Gebruik **flyout Nieuwe** inzending die wordt weergegeven om het bericht, de URL of de bijlage in te dienen, zoals wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="b903e-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b903e-127">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="b903e-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="b903e-128">Selecteer **e-mail** in de sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="b903e-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="b903e-129">Gebruik in **de sectie Inzendingsindeling** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="b903e-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="b903e-130">**Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de **koptekst X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="b903e-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="b903e-131">**Bestand:** Klik op **Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="b903e-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="b903e-132">Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="b903e-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b903e-133">De mogelijkheid om berichten zo oud als 30 dagen in te dienen, is tijdelijk opgeschort voor Defender voor Office 365-klanten.</span><span class="sxs-lookup"><span data-stu-id="b903e-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="b903e-134">Beheerders kunnen slechts 7 dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="b903e-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="b903e-135">Geef in **de sectie Geadresseerden** een of meer geadresseerden op tegen wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b903e-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="b903e-136">Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="b903e-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="b903e-137">Selecteer in **de sectie** Reden voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="b903e-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b903e-138">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="b903e-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b903e-139">**Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="b903e-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="b903e-140">Als u het niet zeker weet, gebruikt u uw beste beoordeling.</span><span class="sxs-lookup"><span data-stu-id="b903e-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="b903e-141">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="b903e-141">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b903e-143">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="b903e-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="b903e-144">Selecteer URL in de sectie **Objecttype.** </span><span class="sxs-lookup"><span data-stu-id="b903e-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="b903e-145">Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="b903e-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="b903e-146">Selecteer in **de sectie** Reden voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="b903e-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b903e-147">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="b903e-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b903e-148">**Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="b903e-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="b903e-149">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="b903e-149">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van e-mail indienen](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b903e-151">Een verdacht bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="b903e-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="b903e-152">Selecteer bijlage in de sectie **Objecttype.** </span><span class="sxs-lookup"><span data-stu-id="b903e-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="b903e-153">Klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="b903e-153">Click **Choose File**.</span></span> <span data-ttu-id="b903e-154">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="b903e-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="b903e-155">Selecteer in **de sectie** Reden voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="b903e-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="b903e-156">**Had niet moeten worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="b903e-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="b903e-157">**Moet zijn geblokkeerd:** **Malware** is de enige keuze en wordt automatisch geselecteerd..</span><span class="sxs-lookup"><span data-stu-id="b903e-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="b903e-158">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="b903e-158">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="b903e-160">Items weergeven die zijn ingediend voor analyse</span><span class="sxs-lookup"><span data-stu-id="b903e-160">View items Submitted for analysis</span></span>

<span data-ttu-id="b903e-161">Ga in & Beveiligingscentrum naar Inzendingen voor  \> **bedreigingsbeheer,** controleer of u zich op het tabblad **Ingediend voor analyse** hebt</span><span class="sxs-lookup"><span data-stu-id="b903e-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="b903e-162">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Indienings-id **(een** GUID-waarde die aan elke inzending is toegewezen) door een waarde in het vak in te voeren en op Knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="b903e-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b903e-163">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="b903e-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b903e-164">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indiening-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="b903e-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="b903e-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b903e-165">**Sender**</span></span>
- <span data-ttu-id="b903e-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="b903e-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="b903e-167">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="b903e-167">**Submitted by**</span></span>
- <span data-ttu-id="b903e-168">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-168">**Submission type**</span></span>
- <span data-ttu-id="b903e-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="b903e-169">**Status**</span></span>

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="b903e-171">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="b903e-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b903e-172">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b903e-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="b903e-173">Onder de grafiek vindt u drie tabbladen: **E-mail** (standaard), **URL** en **Bijlage.**</span><span class="sxs-lookup"><span data-stu-id="b903e-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="b903e-174">E-mailberichten van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="b903e-174">View admin email submissions</span></span>

<span data-ttu-id="b903e-175">Klik op **het tabblad E-mail.**</span><span class="sxs-lookup"><span data-stu-id="b903e-175">Click the **Email** tab.</span></span>

<span data-ttu-id="b903e-176">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="b903e-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b903e-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b903e-177">**Date**</span></span>
- <span data-ttu-id="b903e-178">**Inzending-id:** een GUID-waarde die aan elke inzending is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b903e-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="b903e-179">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-180">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-181">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b903e-181">**Sender**</span></span>
- <span data-ttu-id="b903e-182">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-183">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-183">**Submission type**</span></span>
- <span data-ttu-id="b903e-184">**Bezorgingsreden**</span><span class="sxs-lookup"><span data-stu-id="b903e-184">**Delivery reason**</span></span>
- <span data-ttu-id="b903e-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b903e-186"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="b903e-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="b903e-187">Details van de inzending van beheerders opnieuw scannen</span><span class="sxs-lookup"><span data-stu-id="b903e-187">Admin submission rescan details</span></span>

<span data-ttu-id="b903e-188">Berichten die worden verzonden in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de details flyout:</span><span class="sxs-lookup"><span data-stu-id="b903e-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="b903e-189">Of er tijdens de levering een fout zat in de e-mailverificatie van de afzender.</span><span class="sxs-lookup"><span data-stu-id="b903e-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="b903e-190">Informatie over eventuele beleidstreffers die het oordeel over een bericht kunnen hebben beïnvloed of overschreven.</span><span class="sxs-lookup"><span data-stu-id="b903e-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="b903e-191">Huidige deactiveringsresultaten om te zien of de URL's of bestanden in het bericht schadelijk waren of niet.</span><span class="sxs-lookup"><span data-stu-id="b903e-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="b903e-192">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="b903e-192">Feedback from graders.</span></span>

<span data-ttu-id="b903e-193">Als een overschrijving is gevonden, zou het opnieuw scannen in enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="b903e-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="b903e-194">Als er geen probleem was bij e-mailverificatie of bezorging werd niet beïnvloed door een overschrijven, kan de feedback van cijferaars maximaal een dag duren.</span><span class="sxs-lookup"><span data-stu-id="b903e-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="b903e-195">URL-inzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="b903e-195">View admin URL submissions</span></span>

<span data-ttu-id="b903e-196">Klik op **het tabblad URL.**</span><span class="sxs-lookup"><span data-stu-id="b903e-196">Click the **URL** tab.</span></span>

<span data-ttu-id="b903e-197">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="b903e-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b903e-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b903e-198">**Date**</span></span>
- <span data-ttu-id="b903e-199">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="b903e-199">**Submission ID**</span></span>
- <span data-ttu-id="b903e-200">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-202">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-202">**Submission type**</span></span>
- <span data-ttu-id="b903e-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b903e-204"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="b903e-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="b903e-205">Bijlagen van beheerders bekijken</span><span class="sxs-lookup"><span data-stu-id="b903e-205">View admin attachment submissions</span></span>

<span data-ttu-id="b903e-206">Klik op **het tabblad** Bijlagen.</span><span class="sxs-lookup"><span data-stu-id="b903e-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="b903e-207">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="b903e-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b903e-208">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b903e-208">**Date**</span></span>
- <span data-ttu-id="b903e-209">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="b903e-209">**Submission ID**</span></span>
- <span data-ttu-id="b903e-210">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-211">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-212">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-212">**Submission type**</span></span>
- <span data-ttu-id="b903e-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="b903e-214"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="b903e-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="b903e-215">Gebruikersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="b903e-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="b903e-216">Als u de invoegversie van rapportbericht, de [invoegversie](enable-the-report-message-add-in.md)van [Rapport phishing](enable-the-report-phish-add-in.md)of personen de ingebouwde rapportage in de  [webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)van Outlook hebt geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Gebruikersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="b903e-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="b903e-217">Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="b903e-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="b903e-218">Selecteer het **tabblad Gebruikersinzendingen** en klik vervolgens op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="b903e-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="b903e-219">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="b903e-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b903e-220">**Verzonden op**</span><span class="sxs-lookup"><span data-stu-id="b903e-220">**Submitted on**</span></span>
- <span data-ttu-id="b903e-221">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-222">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-223">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b903e-223">**Sender**</span></span>
- <span data-ttu-id="b903e-224">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-225">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-225">**Submission type**</span></span>

<span data-ttu-id="b903e-226"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="b903e-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="b903e-227">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Afzender door een waarde in het vak in te voeren en op knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="b903e-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b903e-228">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="b903e-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b903e-229">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="b903e-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="b903e-230">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="b903e-230">**Sender domain**</span></span>
- <span data-ttu-id="b903e-231">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="b903e-231">**Subject**</span></span>
- <span data-ttu-id="b903e-232">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="b903e-232">**Submitted by**</span></span>
- <span data-ttu-id="b903e-233">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-233">**Submission type**</span></span>
- <span data-ttu-id="b903e-234">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="b903e-234">**Sender IP**</span></span>

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="b903e-236">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="b903e-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b903e-237">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b903e-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="b903e-238">Gebruikersinzendingen weergeven in het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="b903e-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="b903e-239">**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, kunt u berichten bekijken en verzenden die zijn bezorgd in het rapportpostvak.</span><span class="sxs-lookup"><span data-stu-id="b903e-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="b903e-240">Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="b903e-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="b903e-241">Selecteer het **tabblad Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="b903e-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="b903e-242">U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="b903e-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="b903e-243">**Verzonden op**</span><span class="sxs-lookup"><span data-stu-id="b903e-243">**Submitted on**</span></span>
- <span data-ttu-id="b903e-244">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-245">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-246">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="b903e-246">**Sender**</span></span>
- <span data-ttu-id="b903e-247">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b903e-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="b903e-248">**Inzendingstype**</span><span class="sxs-lookup"><span data-stu-id="b903e-248">**Submission type**</span></span>

<span data-ttu-id="b903e-249">Boven aan de pagina kunt u een begindatum, een einddatum  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op knop ![ Vernieuwen te ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="b903e-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="b903e-250">U kunt meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="b903e-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="b903e-251">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="b903e-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="b903e-252">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b903e-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="b903e-253">Als organisaties zijn geconfigureerd om alleen naar een aangepast postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in de portal Gebruikers gerapporteerde berichten altijd leeg.</span><span class="sxs-lookup"><span data-stu-id="b903e-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="b903e-254">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="b903e-254">Undo user submissions</span></span>

<span data-ttu-id="b903e-255">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="b903e-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="b903e-256">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="b903e-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="b903e-257">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="b903e-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="b903e-258">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="b903e-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="b903e-259">Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.</span><span class="sxs-lookup"><span data-stu-id="b903e-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="b903e-260">Selecteer op **het tabblad** Aangepast postvak een  bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="b903e-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="b903e-261">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="b903e-261">**Report clean**</span></span>
- <span data-ttu-id="b903e-262">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="b903e-262">**Report phishing**</span></span>
- <span data-ttu-id="b903e-263">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="b903e-263">**Report malware**</span></span>
- <span data-ttu-id="b903e-264">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="b903e-264">**Report spam**</span></span>

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
