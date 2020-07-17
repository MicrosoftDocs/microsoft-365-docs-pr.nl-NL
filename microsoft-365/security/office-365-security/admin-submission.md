---
title: Beheerdersinzendingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze de portal Voor inzendingen in het Security & Compliance Center kunnen gebruiken om verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden bij Microsoft in te dienen om te scannen.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726848"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="058eb-103">Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="058eb-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="058eb-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Submissions in het Security & Compliance Center gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen om te scannen.</span><span class="sxs-lookup"><span data-stu-id="058eb-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="058eb-105">Wanneer u een e-mail indient, ontvangt u informatie over beleidsregels die de binnenkomende e-mail mogelijk hebben toegestaan bij uw tenant, evenals het onderzoeken van URL's en bijlagen in de e-mail.</span><span class="sxs-lookup"><span data-stu-id="058eb-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="058eb-106">Beleidsregels die een e-mail mogelijk hebben toegestaan, bevatten de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals Exchange-e-mailstroomregels (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="058eb-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="058eb-107">Zie [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, URL's en bijlagen naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="058eb-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="058eb-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="058eb-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="058eb-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="058eb-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="058eb-110">Als u rechtstreeks naar de **pagina Indiening** wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="058eb-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="058eb-111">U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="058eb-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="058eb-112">Als u berichten en bestanden wilt verzenden bij Microsoft, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="058eb-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="058eb-113">**Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="058eb-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="058eb-114">**Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="058eb-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="058eb-115">Voor alleen-lezen toegang tot de portal Voor inzendingen moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="058eb-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="058eb-116">**Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="058eb-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="058eb-117">**Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="058eb-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="058eb-118">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)meer informatie over hoe gebruikers berichten en bestanden naar Microsoft kunnen verzenden.</span><span class="sxs-lookup"><span data-stu-id="058eb-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="058eb-119">Verdachte inhoud melden aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="058eb-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="058eb-120">Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.</span><span class="sxs-lookup"><span data-stu-id="058eb-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="058eb-121">Klik op de pagina **Inzendingen** die wordt weergegeven op de knop **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="058eb-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="058eb-122">Gebruik de flyout **voor nieuwe indiening** die het bericht, de URL of de bijlage lijkt in te dienen, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="058eb-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="058eb-123">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="058eb-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="058eb-124">Selecteer **E-mail**in de sectie **Objecttype** .</span><span class="sxs-lookup"><span data-stu-id="058eb-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="058eb-125">Gebruik in de sectie **Weergave een** van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="058eb-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="058eb-126">**Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de kop **X-MS-Exchange-Organization-Network-Message-Id** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="058eb-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="058eb-127">**Bestand**: Klik op **Bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="058eb-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="058eb-128">Zoek en selecteer in het dialoogvenster dat het .eml- of .msg-bestand opent en klik vervolgens op **Openen**.</span><span class="sxs-lookup"><span data-stu-id="058eb-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="058eb-129">Geef in de sectie **Geadresseerden** een of meer ontvangers op waartegen u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="058eb-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="058eb-130">De beleidscontrole bepaalt of de e-mail het scannen heeft omzeild vanwege het gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="058eb-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="058eb-131">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="058eb-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="058eb-132">**Had niet geblokkeerd moeten worden**</span><span class="sxs-lookup"><span data-stu-id="058eb-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="058eb-133">**Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing**of **Malware**.</span><span class="sxs-lookup"><span data-stu-id="058eb-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="058eb-134">Als je het niet zeker weet, gebruik dan je beste oordeel.</span><span class="sxs-lookup"><span data-stu-id="058eb-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="058eb-135">Als het filter is omzeild vanwege beleid bij indiening, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="058eb-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="058eb-136">Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="058eb-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="058eb-137">U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken.</span><span class="sxs-lookup"><span data-stu-id="058eb-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="058eb-138">Dit omvat de resultaten van de beleidscontrole en het herscanvonnis.</span><span class="sxs-lookup"><span data-stu-id="058eb-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="058eb-139">Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstapel van Office 365 ATP, maar een gedeeltelijke rescan uitvoert op basis van bepaalde kenmerken van de e-mail, URL of bestand.</span><span class="sxs-lookup"><span data-stu-id="058eb-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="058eb-140">Als u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="058eb-140">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="058eb-142">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="058eb-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="058eb-143">Selecteer **URL**in de sectie **Objecttype** .</span><span class="sxs-lookup"><span data-stu-id="058eb-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="058eb-144">Voer in het vak dat wordt weergegeven de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="058eb-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="058eb-145">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="058eb-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="058eb-146">**Had niet geblokkeerd moeten worden**</span><span class="sxs-lookup"><span data-stu-id="058eb-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="058eb-147">**Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware**.</span><span class="sxs-lookup"><span data-stu-id="058eb-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="058eb-148">Als u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="058eb-148">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="058eb-150">Een verdacht bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="058eb-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="058eb-151">Selecteer bijlage in de sectie **Objecttype** **.**</span><span class="sxs-lookup"><span data-stu-id="058eb-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="058eb-152">Klik **op Bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="058eb-152">Click **Choose File**.</span></span> <span data-ttu-id="058eb-153">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en selecteer het bestand en klik vervolgens op **Openen**.</span><span class="sxs-lookup"><span data-stu-id="058eb-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="058eb-154">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="058eb-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="058eb-155">**Had niet geblokkeerd moeten worden**</span><span class="sxs-lookup"><span data-stu-id="058eb-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="058eb-156">**Moet zijn geblokkeerd**: **Malware** is de enige keuze, en wordt automatisch geselecteerd..</span><span class="sxs-lookup"><span data-stu-id="058eb-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="058eb-157">Als u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="058eb-157">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="058eb-159">Beheerdersinzendingen bekijken</span><span class="sxs-lookup"><span data-stu-id="058eb-159">View admin submissions</span></span>

1. <span data-ttu-id="058eb-160">Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.</span><span class="sxs-lookup"><span data-stu-id="058eb-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="058eb-161">Controleer op de pagina **Inzendingen** dat wordt weergegeven of het tabblad **Beheerdersinzendingen** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="058eb-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="058eb-162">Boven aan de pagina u een begindatum, een einddatum invoeren en (standaard) u filteren op **inzendings-id** door een waarde in het vak in te voeren en op vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="058eb-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="058eb-163">U meerdere waarden invoeren die door komma's zijn gescheiden.</span><span class="sxs-lookup"><span data-stu-id="058eb-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="058eb-164">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indienings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="058eb-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="058eb-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="058eb-165">**Sender**</span></span>
- <span data-ttu-id="058eb-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="058eb-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="058eb-167">**Afkomstig**</span><span class="sxs-lookup"><span data-stu-id="058eb-167">**Submitted by**</span></span>
- <span data-ttu-id="058eb-168">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-168">**Submission type**</span></span>
- <span data-ttu-id="058eb-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="058eb-169">**Status**</span></span>

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="058eb-171">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**.</span><span class="sxs-lookup"><span data-stu-id="058eb-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="058eb-172">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="058eb-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="058eb-173">Onder de grafiek bevinden zich drie tabbladen: **E-mail** (standaard), **URL**en **Bijlage**.</span><span class="sxs-lookup"><span data-stu-id="058eb-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="058eb-174">E-mailinzendingen voor beheerders bekijken</span><span class="sxs-lookup"><span data-stu-id="058eb-174">View admin email submissions</span></span>

<span data-ttu-id="058eb-175">Klik op het tabblad **E-mail.**</span><span class="sxs-lookup"><span data-stu-id="058eb-175">Click the **Email** tab.</span></span>

<span data-ttu-id="058eb-176">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="058eb-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="058eb-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="058eb-177">**Date**</span></span>
- <span data-ttu-id="058eb-178">**Indienings-id**</span><span class="sxs-lookup"><span data-stu-id="058eb-178">**Submission ID**</span></span>
- <span data-ttu-id="058eb-179">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-180">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-181">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="058eb-181">**Sender**</span></span>
- <span data-ttu-id="058eb-182">**IP-adres van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-183">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-183">**Submission type**</span></span>
- <span data-ttu-id="058eb-184">**Reden voor levering**</span><span class="sxs-lookup"><span data-stu-id="058eb-184">**Delivery reason**</span></span>
- <span data-ttu-id="058eb-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-186">**Besturingstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-186">**Control type**</span></span>
- <span data-ttu-id="058eb-187">**Controlebron**</span><span class="sxs-lookup"><span data-stu-id="058eb-187">**Control source**</span></span>

  <span data-ttu-id="058eb-188"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="058eb-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="058eb-189">Beheerders-URL-inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="058eb-189">View admin URL submissions</span></span>

<span data-ttu-id="058eb-190">Klik op het tabblad **URL.**</span><span class="sxs-lookup"><span data-stu-id="058eb-190">Click the **URL** tab.</span></span>

<span data-ttu-id="058eb-191">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="058eb-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="058eb-192">**Datum**</span><span class="sxs-lookup"><span data-stu-id="058eb-192">**Date**</span></span>
- <span data-ttu-id="058eb-193">**Indienings-id**</span><span class="sxs-lookup"><span data-stu-id="058eb-193">**Submission ID**</span></span>
- <span data-ttu-id="058eb-194">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-195">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-196">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-196">**Submission type**</span></span>
- <span data-ttu-id="058eb-197">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="058eb-198"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="058eb-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="058eb-199">Beheerdersbijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="058eb-199">View admin attachment submissions</span></span>

<span data-ttu-id="058eb-200">Klik op het tabblad **Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="058eb-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="058eb-201">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="058eb-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="058eb-202">**Datum**</span><span class="sxs-lookup"><span data-stu-id="058eb-202">**Date**</span></span>
- <span data-ttu-id="058eb-203">**Indienings-id**</span><span class="sxs-lookup"><span data-stu-id="058eb-203">**Submission ID**</span></span>
- <span data-ttu-id="058eb-204">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-205">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-206">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-206">**Submission type**</span></span>
- <span data-ttu-id="058eb-207">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="058eb-208"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="058eb-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="058eb-209">Gebruikersinzendingen bij Microsoft weergeven</span><span class="sxs-lookup"><span data-stu-id="058eb-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="058eb-210">Als u de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)hebt geïmplementeerd of als mensen de [ingebouwde rapportage in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)van Outlook gebruiken, u zien wat gebruikers rapporteren op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="058eb-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="058eb-211">Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.</span><span class="sxs-lookup"><span data-stu-id="058eb-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="058eb-212">Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="058eb-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="058eb-213">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="058eb-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="058eb-214">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="058eb-214">**Submitted on**</span></span>
- <span data-ttu-id="058eb-215">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-216">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-217">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="058eb-217">**Sender**</span></span>
- <span data-ttu-id="058eb-218">**IP-adres van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-219">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-219">**Submission type**</span></span>

<span data-ttu-id="058eb-220"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="058eb-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="058eb-221">Boven aan de pagina u een begindatum, een einddatum invoeren en (standaard) u filteren op **afzender** door een waarde in het vak in te voeren en op vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="058eb-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="058eb-222">U meerdere waarden invoeren die door komma's zijn gescheiden.</span><span class="sxs-lookup"><span data-stu-id="058eb-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="058eb-223">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="058eb-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="058eb-224">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="058eb-224">**Sender domain**</span></span>
- <span data-ttu-id="058eb-225">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="058eb-225">**Subject**</span></span>
- <span data-ttu-id="058eb-226">**Afkomstig**</span><span class="sxs-lookup"><span data-stu-id="058eb-226">**Submitted by**</span></span>
- <span data-ttu-id="058eb-227">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-227">**Submission type**</span></span>
- <span data-ttu-id="058eb-228">**IP-adres van afzender**</span><span class="sxs-lookup"><span data-stu-id="058eb-228">**Sender IP**</span></span>

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="058eb-230">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**.</span><span class="sxs-lookup"><span data-stu-id="058eb-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="058eb-231">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="058eb-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="058eb-232">Gebruikersinzendingen weergeven in het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="058eb-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="058eb-233">Als u [een aangepast postvak](user-submission.md) hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, u berichten bekijken en verzenden die zijn bezorgd in het rapportpostvak.</span><span class="sxs-lookup"><span data-stu-id="058eb-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="058eb-234">Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.</span><span class="sxs-lookup"><span data-stu-id="058eb-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="058eb-235">Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="058eb-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="058eb-236">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="058eb-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="058eb-237">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="058eb-237">**Submitted on**</span></span>
- <span data-ttu-id="058eb-238">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-239">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-240">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="058eb-240">**Sender**</span></span>
- <span data-ttu-id="058eb-241">**IP-adres van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="058eb-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="058eb-242">**Indieningstype**</span><span class="sxs-lookup"><span data-stu-id="058eb-242">**Submission type**</span></span>

<span data-ttu-id="058eb-243">Boven aan de pagina u een begindatum, een einddatum invoeren en u filteren op **Ingezonden door** een waarde in het vak in te voeren en op Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="058eb-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="058eb-244">U meerdere waarden invoeren die door komma's zijn gescheiden.</span><span class="sxs-lookup"><span data-stu-id="058eb-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="058eb-245">Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**.</span><span class="sxs-lookup"><span data-stu-id="058eb-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="058eb-246">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="058eb-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="058eb-247">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="058eb-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="058eb-248">Als u het aangepaste postvak hebt geconfigureerd om door gebruikers gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, u specifieke berichten voor analyse naar Microsoft zoeken en verzenden.</span><span class="sxs-lookup"><span data-stu-id="058eb-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="058eb-249">Hierdoor wordt een gebruiker effectief naar een beheerdersinzending verplaatst.</span><span class="sxs-lookup"><span data-stu-id="058eb-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="058eb-250">Selecteer op het tabblad **Aangepast postvak** een bericht in de lijst, klik op de knop **Actie** en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="058eb-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="058eb-251">**Rapport schoon**</span><span class="sxs-lookup"><span data-stu-id="058eb-251">**Report clean**</span></span>
- <span data-ttu-id="058eb-252">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="058eb-252">**Report phishing**</span></span>
- <span data-ttu-id="058eb-253">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="058eb-253">**Report malware**</span></span>
- <span data-ttu-id="058eb-254">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="058eb-254">**Report spam**</span></span>

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
