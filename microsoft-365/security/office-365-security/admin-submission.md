---
title: Admin-inzendingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie over het gebruik van de portal voor uitnodigingen van de beveiligings & nalevings centrum voor het verzenden van verdachte e-mailberichten, verdachte e-mailberichten, spam en andere mogelijk schadelijke berichten, Url's en bestanden aan Microsoft voor het scannen.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845964"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="940c1-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="940c1-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="940c1-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="940c1-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="940c1-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="940c1-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="940c1-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="940c1-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="940c1-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="940c1-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="940c1-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="940c1-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="940c1-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="940c1-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="940c1-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="940c1-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="940c1-111">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="940c1-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="940c1-112">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="940c1-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="940c1-113">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="940c1-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="940c1-114">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="940c1-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="940c1-115">Voor alleen-lezen toegang tot de portal van ingediende items moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="940c1-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="940c1-116">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="940c1-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="940c1-117">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="940c1-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="940c1-118">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="940c1-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="940c1-119">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="940c1-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="940c1-120">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="940c1-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="940c1-121">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="940c1-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="940c1-122">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="940c1-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="940c1-123">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="940c1-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="940c1-124">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="940c1-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="940c1-125">**Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="940c1-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="940c1-126">**Bestand**: Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="940c1-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="940c1-127">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="940c1-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="940c1-128">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="940c1-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="940c1-129">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="940c1-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="940c1-130">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="940c1-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="940c1-131">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="940c1-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="940c1-132">**Is geblokkeerd**: Selecteer **spam**, **phishing**of **malware**.</span><span class="sxs-lookup"><span data-stu-id="940c1-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="940c1-133">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="940c1-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="940c1-134">Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="940c1-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="940c1-135">Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="940c1-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="940c1-136">Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending.</span><span class="sxs-lookup"><span data-stu-id="940c1-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="940c1-137">Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict.</span><span class="sxs-lookup"><span data-stu-id="940c1-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="940c1-138">Opmerking Hiermee wordt de e-mail niet uitgevoerd via de Office 365 ATP-stack voor volledig filteren, maar wordt een gedeeltelijk herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="940c1-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="940c1-139">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="940c1-139">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="940c1-141">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="940c1-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="940c1-142">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="940c1-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="940c1-143">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="940c1-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="940c1-144">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="940c1-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="940c1-145">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="940c1-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="940c1-146">**Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="940c1-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="940c1-147">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="940c1-147">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="940c1-149">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="940c1-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="940c1-150">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="940c1-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="940c1-151">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="940c1-151">Click **Choose File**.</span></span> <span data-ttu-id="940c1-152">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="940c1-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="940c1-153">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="940c1-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="940c1-154">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="940c1-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="940c1-155">Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="940c1-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="940c1-156">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="940c1-156">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="940c1-158">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="940c1-158">View admin submissions</span></span>

<span data-ttu-id="940c1-159">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="940c1-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="940c1-160">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="940c1-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="940c1-161">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="940c1-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="940c1-162">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="940c1-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="940c1-163">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="940c1-163">**Sender**</span></span>
- <span data-ttu-id="940c1-164">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="940c1-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="940c1-165">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="940c1-165">**Submitted by**</span></span>
- <span data-ttu-id="940c1-166">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-166">**Submission type**</span></span>
- <span data-ttu-id="940c1-167">**Status**</span><span class="sxs-lookup"><span data-stu-id="940c1-167">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="940c1-169">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="940c1-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="940c1-170">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="940c1-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="940c1-171">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL**en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="940c1-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="940c1-172">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="940c1-172">View admin email submissions</span></span>

<span data-ttu-id="940c1-173">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="940c1-173">Click the **Email** tab.</span></span>

<span data-ttu-id="940c1-174">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="940c1-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="940c1-175">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="940c1-175">**Date**</span></span>
- <span data-ttu-id="940c1-176">**Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="940c1-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="940c1-177">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-178">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-179">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="940c1-179">**Sender**</span></span>
- <span data-ttu-id="940c1-180">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-181">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-181">**Submission type**</span></span>
- <span data-ttu-id="940c1-182">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="940c1-182">**Delivery reason**</span></span>
- <span data-ttu-id="940c1-183">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-184">**Typebesturingselement**</span><span class="sxs-lookup"><span data-stu-id="940c1-184">**Control type**</span></span>
- <span data-ttu-id="940c1-185">**Besturingselementbron**</span><span class="sxs-lookup"><span data-stu-id="940c1-185">**Control source**</span></span>

  <span data-ttu-id="940c1-186"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="940c1-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="940c1-187">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="940c1-187">View admin URL submissions</span></span>

<span data-ttu-id="940c1-188">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="940c1-188">Click the **URL** tab.</span></span>

<span data-ttu-id="940c1-189">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="940c1-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="940c1-190">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="940c1-190">**Date**</span></span>
- <span data-ttu-id="940c1-191">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="940c1-191">**Submission ID**</span></span>
- <span data-ttu-id="940c1-192">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-194">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-194">**Submission type**</span></span>
- <span data-ttu-id="940c1-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="940c1-196"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="940c1-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="940c1-197">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="940c1-197">View admin attachment submissions</span></span>

<span data-ttu-id="940c1-198">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="940c1-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="940c1-199">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="940c1-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="940c1-200">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="940c1-200">**Date**</span></span>
- <span data-ttu-id="940c1-201">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="940c1-201">**Submission ID**</span></span>
- <span data-ttu-id="940c1-202">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-203">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-204">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-204">**Submission type**</span></span>
- <span data-ttu-id="940c1-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="940c1-206"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="940c1-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="940c1-207">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="940c1-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="940c1-208">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="940c1-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="940c1-209">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="940c1-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="940c1-210">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.</span><span class="sxs-lookup"><span data-stu-id="940c1-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="940c1-211">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="940c1-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="940c1-212">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="940c1-212">**Submitted on**</span></span>
- <span data-ttu-id="940c1-213">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-214">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-215">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="940c1-215">**Sender**</span></span>
- <span data-ttu-id="940c1-216">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-217">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-217">**Submission type**</span></span>

<span data-ttu-id="940c1-218"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="940c1-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="940c1-219">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="940c1-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="940c1-220">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="940c1-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="940c1-221">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="940c1-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="940c1-222">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="940c1-222">**Sender domain**</span></span>
- <span data-ttu-id="940c1-223">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="940c1-223">**Subject**</span></span>
- <span data-ttu-id="940c1-224">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="940c1-224">**Submitted by**</span></span>
- <span data-ttu-id="940c1-225">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-225">**Submission type**</span></span>
- <span data-ttu-id="940c1-226">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="940c1-226">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="940c1-228">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="940c1-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="940c1-229">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="940c1-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="940c1-230">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="940c1-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="940c1-231">Als u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="940c1-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="940c1-232">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="940c1-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="940c1-233">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="940c1-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="940c1-234">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="940c1-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="940c1-235">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="940c1-235">**Submitted on**</span></span>
- <span data-ttu-id="940c1-236">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-237">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-238">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="940c1-238">**Sender**</span></span>
- <span data-ttu-id="940c1-239">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="940c1-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="940c1-240">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="940c1-240">**Submission type**</span></span>

<span data-ttu-id="940c1-241">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="940c1-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="940c1-242">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="940c1-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="940c1-243">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="940c1-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="940c1-244">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="940c1-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="940c1-245">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="940c1-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="940c1-246">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="940c1-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="940c1-247">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="940c1-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="940c1-248">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="940c1-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="940c1-249">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="940c1-249">**Report clean**</span></span>
- <span data-ttu-id="940c1-250">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="940c1-250">**Report phishing**</span></span>
- <span data-ttu-id="940c1-251">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="940c1-251">**Report malware**</span></span>
- <span data-ttu-id="940c1-252">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="940c1-252">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
