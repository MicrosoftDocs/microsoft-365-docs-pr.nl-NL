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
ms.openlocfilehash: 08d1633142bba7348cbc899f9cf9b2a1288c3743
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394733"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="fca65-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="fca65-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="fca65-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="fca65-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="fca65-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="fca65-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="fca65-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="fca65-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="fca65-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="fca65-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fca65-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="fca65-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fca65-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fca65-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fca65-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="fca65-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="fca65-111">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="fca65-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="fca65-112">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fca65-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="fca65-113">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fca65-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="fca65-114">Houd er rekening mee dat lidmaatschap van deze rollen groep is vereist voor [het weergeven van gebruikers inzendingen aan het aangepaste postvak](#view-user-submissions-to-the-custom-mailbox) , zoals verderop in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="fca65-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="fca65-115">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fca65-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="fca65-116">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="fca65-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="fca65-117">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="fca65-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="fca65-118">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="fca65-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="fca65-119">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="fca65-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="fca65-120">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="fca65-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="fca65-121">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="fca65-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="fca65-122">**Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="fca65-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="fca65-123">**Bestand**: Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="fca65-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="fca65-124">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="fca65-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="fca65-125">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fca65-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="fca65-126">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="fca65-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="fca65-127">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="fca65-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fca65-128">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="fca65-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fca65-129">**Is geblokkeerd**: Selecteer **spam**, **phishing**of **malware**.</span><span class="sxs-lookup"><span data-stu-id="fca65-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="fca65-130">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fca65-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="fca65-131">Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="fca65-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="fca65-132">Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="fca65-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="fca65-133">Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending.</span><span class="sxs-lookup"><span data-stu-id="fca65-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="fca65-134">Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict.</span><span class="sxs-lookup"><span data-stu-id="fca65-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="fca65-135">Opmerking Hiermee wordt de e-mail niet uitgevoerd via de Office 365 ATP-stack voor volledig filteren, maar wordt een gedeeltelijk herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="fca65-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="fca65-136">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="fca65-136">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="fca65-138">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="fca65-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="fca65-139">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="fca65-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="fca65-140">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="fca65-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="fca65-141">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="fca65-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fca65-142">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="fca65-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fca65-143">**Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="fca65-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="fca65-144">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="fca65-144">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="fca65-146">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="fca65-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="fca65-147">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="fca65-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="fca65-148">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="fca65-148">Click **Choose File**.</span></span> <span data-ttu-id="fca65-149">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="fca65-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="fca65-150">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="fca65-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fca65-151">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="fca65-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fca65-152">Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="fca65-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="fca65-153">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="fca65-153">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="fca65-155">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="fca65-155">View admin submissions</span></span>

<span data-ttu-id="fca65-156">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="fca65-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="fca65-157">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fca65-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fca65-158">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="fca65-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fca65-159">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="fca65-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="fca65-160">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="fca65-160">**Sender**</span></span>
- <span data-ttu-id="fca65-161">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="fca65-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="fca65-162">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="fca65-162">**Submitted by**</span></span>
- <span data-ttu-id="fca65-163">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-163">**Submission type**</span></span>
- <span data-ttu-id="fca65-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="fca65-164">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="fca65-166">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="fca65-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fca65-167">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fca65-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="fca65-168">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL**en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="fca65-168">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="fca65-169">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="fca65-169">View admin email submissions</span></span>

<span data-ttu-id="fca65-170">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="fca65-170">Click the **Email** tab.</span></span>

<span data-ttu-id="fca65-171">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="fca65-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fca65-172">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="fca65-172">**Date**</span></span>
- <span data-ttu-id="fca65-173">**Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="fca65-173">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="fca65-174">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-175">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-176">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="fca65-176">**Sender**</span></span>
- <span data-ttu-id="fca65-177">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-178">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-178">**Submission type**</span></span>
- <span data-ttu-id="fca65-179">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="fca65-179">**Delivery reason**</span></span>
- <span data-ttu-id="fca65-180">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-181">**Typebesturingselement**</span><span class="sxs-lookup"><span data-stu-id="fca65-181">**Control type**</span></span>
- <span data-ttu-id="fca65-182">**Besturingselementbron**</span><span class="sxs-lookup"><span data-stu-id="fca65-182">**Control source**</span></span>

  <span data-ttu-id="fca65-183"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="fca65-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="fca65-184">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="fca65-184">View admin URL submissions</span></span>

<span data-ttu-id="fca65-185">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="fca65-185">Click the **URL** tab.</span></span>

<span data-ttu-id="fca65-186">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="fca65-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fca65-187">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="fca65-187">**Date**</span></span>
- <span data-ttu-id="fca65-188">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="fca65-188">**Submission ID**</span></span>
- <span data-ttu-id="fca65-189">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-191">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-191">**Submission type**</span></span>
- <span data-ttu-id="fca65-192">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fca65-193"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="fca65-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="fca65-194">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="fca65-194">View admin attachment submissions</span></span>

<span data-ttu-id="fca65-195">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="fca65-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="fca65-196">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="fca65-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fca65-197">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="fca65-197">**Date**</span></span>
- <span data-ttu-id="fca65-198">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="fca65-198">**Submission ID**</span></span>
- <span data-ttu-id="fca65-199">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-200">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-201">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-201">**Submission type**</span></span>
- <span data-ttu-id="fca65-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fca65-203"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="fca65-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="fca65-204">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="fca65-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="fca65-205">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="fca65-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="fca65-206">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="fca65-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fca65-207">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.</span><span class="sxs-lookup"><span data-stu-id="fca65-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="fca65-208">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="fca65-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fca65-209">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="fca65-209">**Submitted on**</span></span>
- <span data-ttu-id="fca65-210">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-211">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-212">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="fca65-212">**Sender**</span></span>
- <span data-ttu-id="fca65-213">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-214">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-214">**Submission type**</span></span>

<span data-ttu-id="fca65-215"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="fca65-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="fca65-216">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fca65-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fca65-217">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="fca65-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fca65-218">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="fca65-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="fca65-219">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="fca65-219">**Sender domain**</span></span>
- <span data-ttu-id="fca65-220">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="fca65-220">**Subject**</span></span>
- <span data-ttu-id="fca65-221">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="fca65-221">**Submitted by**</span></span>
- <span data-ttu-id="fca65-222">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-222">**Submission type**</span></span>
- <span data-ttu-id="fca65-223">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="fca65-223">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="fca65-225">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="fca65-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fca65-226">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fca65-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="fca65-227">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="fca65-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="fca65-228">**Als** u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="fca65-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="fca65-229">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="fca65-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fca65-230">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="fca65-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="fca65-231">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="fca65-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fca65-232">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="fca65-232">**Submitted on**</span></span>
- <span data-ttu-id="fca65-233">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-234">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-235">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="fca65-235">**Sender**</span></span>
- <span data-ttu-id="fca65-236">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fca65-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fca65-237">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="fca65-237">**Submission type**</span></span>

<span data-ttu-id="fca65-238">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="fca65-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fca65-239">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="fca65-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fca65-240">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="fca65-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fca65-241">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fca65-241">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="fca65-242">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="fca65-242">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="fca65-243">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="fca65-243">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="fca65-244">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="fca65-244">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="fca65-245">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="fca65-245">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="fca65-246">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="fca65-246">**Report clean**</span></span>
- <span data-ttu-id="fca65-247">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="fca65-247">**Report phishing**</span></span>
- <span data-ttu-id="fca65-248">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="fca65-248">**Report malware**</span></span>
- <span data-ttu-id="fca65-249">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="fca65-249">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
