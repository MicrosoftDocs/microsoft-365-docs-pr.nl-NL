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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie over het gebruik van de portal voor uitnodigingen van de beveiligings & nalevings centrum voor het verzenden van verdachte e-mailberichten, verdachte e-mailberichten, spam en andere mogelijk schadelijke berichten, Url's en bestanden aan Microsoft voor het scannen.
ms.openlocfilehash: 5d4123acaf3c9891f9aeb8028173f3071c260935
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806758"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="afbed-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="afbed-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="afbed-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="afbed-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="afbed-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="afbed-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="afbed-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="afbed-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="afbed-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="afbed-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="afbed-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="afbed-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="afbed-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="afbed-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="afbed-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="afbed-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="afbed-111">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="afbed-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="afbed-112">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="afbed-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="afbed-113">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="afbed-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="afbed-114">Houd er rekening mee dat lidmaatschap van deze rollen groep is vereist voor [het weergeven van gebruikers inzendingen aan het aangepaste postvak](#view-user-submissions-to-the-custom-mailbox) , zoals verderop in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="afbed-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="afbed-115">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="afbed-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="afbed-116">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="afbed-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="afbed-117">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions** , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission** .</span></span>

2. <span data-ttu-id="afbed-118">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="afbed-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="afbed-119">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="afbed-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="afbed-120">Selecteer in de sectie **object type** de optie **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="afbed-120">In the **Object type** section, select **Email** .</span></span> <span data-ttu-id="afbed-121">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="afbed-122">**Netwerkbericht-id** : dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="afbed-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="afbed-123">**Bestand** : Klik op **bestand kiezen** .</span><span class="sxs-lookup"><span data-stu-id="afbed-123">**File** : Click **Choose file** .</span></span> <span data-ttu-id="afbed-124">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen** .</span><span class="sxs-lookup"><span data-stu-id="afbed-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open** .</span></span>

2. <span data-ttu-id="afbed-125">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="afbed-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="afbed-126">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="afbed-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="afbed-127">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="afbed-128">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="afbed-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="afbed-129">**Is geblokkeerd** : Selecteer **spam** , **phishing** of **malware** .</span><span class="sxs-lookup"><span data-stu-id="afbed-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware** .</span></span> <span data-ttu-id="afbed-130">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="afbed-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="afbed-131">Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="afbed-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="afbed-132">Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="afbed-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="afbed-133">Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending.</span><span class="sxs-lookup"><span data-stu-id="afbed-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="afbed-134">Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict.</span><span class="sxs-lookup"><span data-stu-id="afbed-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="afbed-135">Opmerking Hiermee wordt de e-mail niet uitgevoerd via de Office 365 ATP-stack voor volledig filteren, maar wordt een gedeeltelijk herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="afbed-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="afbed-136">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="afbed-136">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="afbed-138">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="afbed-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="afbed-139">Selecteer in de sectie **object type** de optie **URL** .</span><span class="sxs-lookup"><span data-stu-id="afbed-139">In the **Object type** section, select **URL** .</span></span> <span data-ttu-id="afbed-140">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="afbed-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="afbed-141">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="afbed-142">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="afbed-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="afbed-143">**Moet zijn geblokkeerd** : Selecteer **phishing** of **malware** .</span><span class="sxs-lookup"><span data-stu-id="afbed-143">**Should have been blocked** : Select **Phishing** or **Malware** .</span></span>

3. <span data-ttu-id="afbed-144">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="afbed-144">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="afbed-146">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="afbed-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="afbed-147">Selecteer in de sectie **object type** de optie **bijlage** .</span><span class="sxs-lookup"><span data-stu-id="afbed-147">In the **Object type** section, select **Attachment** .</span></span>

2. <span data-ttu-id="afbed-148">Klik op **bestand kiezen** .</span><span class="sxs-lookup"><span data-stu-id="afbed-148">Click **Choose File** .</span></span> <span data-ttu-id="afbed-149">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen** .</span><span class="sxs-lookup"><span data-stu-id="afbed-149">In the dialog that opens, find and select the file, and then click **Open** .</span></span>

3. <span data-ttu-id="afbed-150">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="afbed-151">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="afbed-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="afbed-152">Is **geblokkeerd** : **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="afbed-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="afbed-153">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="afbed-153">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="afbed-155">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="afbed-155">View admin submissions</span></span>

<span data-ttu-id="afbed-156">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions** , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening** .</span><span class="sxs-lookup"><span data-stu-id="afbed-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission** .</span></span>

<span data-ttu-id="afbed-157">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="afbed-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="afbed-158">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="afbed-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="afbed-159">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="afbed-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="afbed-160">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="afbed-160">**Sender**</span></span>
- <span data-ttu-id="afbed-161">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="afbed-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="afbed-162">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="afbed-162">**Submitted by**</span></span>
- <span data-ttu-id="afbed-163">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-163">**Submission type**</span></span>
- <span data-ttu-id="afbed-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="afbed-164">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="afbed-166">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="afbed-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="afbed-167">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="afbed-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="afbed-168">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL** en **bijlage** .</span><span class="sxs-lookup"><span data-stu-id="afbed-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment** .</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="afbed-169">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="afbed-169">View admin email submissions</span></span>

<span data-ttu-id="afbed-170">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="afbed-170">Click the **Email** tab.</span></span>

<span data-ttu-id="afbed-171">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="afbed-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="afbed-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="afbed-172">**Date**</span></span>
- <span data-ttu-id="afbed-173">**Ingediende id** : een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="afbed-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="afbed-174">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-175">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-176">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="afbed-176">**Sender**</span></span>
- <span data-ttu-id="afbed-177">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-178">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-178">**Submission type**</span></span>
- <span data-ttu-id="afbed-179">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="afbed-179">**Delivery reason**</span></span>
- <span data-ttu-id="afbed-180">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-181">**Typebesturingselement**</span><span class="sxs-lookup"><span data-stu-id="afbed-181">**Control type**</span></span>
- <span data-ttu-id="afbed-182">**Besturingselementbron**</span><span class="sxs-lookup"><span data-stu-id="afbed-182">**Control source**</span></span>

  <span data-ttu-id="afbed-183"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="afbed-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="afbed-184">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="afbed-184">View admin URL submissions</span></span>

<span data-ttu-id="afbed-185">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="afbed-185">Click the **URL** tab.</span></span>

<span data-ttu-id="afbed-186">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="afbed-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="afbed-187">**Datum**</span><span class="sxs-lookup"><span data-stu-id="afbed-187">**Date**</span></span>
- <span data-ttu-id="afbed-188">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="afbed-188">**Submission ID**</span></span>
- <span data-ttu-id="afbed-189">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-191">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-191">**Submission type**</span></span>
- <span data-ttu-id="afbed-192">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="afbed-193"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="afbed-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="afbed-194">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="afbed-194">View admin attachment submissions</span></span>

<span data-ttu-id="afbed-195">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="afbed-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="afbed-196">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="afbed-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="afbed-197">**Datum**</span><span class="sxs-lookup"><span data-stu-id="afbed-197">**Date**</span></span>
- <span data-ttu-id="afbed-198">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="afbed-198">**Submission ID**</span></span>
- <span data-ttu-id="afbed-199">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-200">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-201">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-201">**Submission type**</span></span>
- <span data-ttu-id="afbed-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="afbed-203"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="afbed-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="afbed-204">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="afbed-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="afbed-205">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="afbed-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="afbed-206">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions** .</span><span class="sxs-lookup"><span data-stu-id="afbed-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions** .</span></span>

2. <span data-ttu-id="afbed-207">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending** .</span><span class="sxs-lookup"><span data-stu-id="afbed-207">Select the **User submissions** tab, and then click **New submission** .</span></span>

<span data-ttu-id="afbed-208">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="afbed-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="afbed-209">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="afbed-209">**Submitted on**</span></span>
- <span data-ttu-id="afbed-210">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-211">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-212">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="afbed-212">**Sender**</span></span>
- <span data-ttu-id="afbed-213">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-214">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-214">**Submission type**</span></span>

<span data-ttu-id="afbed-215"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="afbed-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="afbed-216">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="afbed-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="afbed-217">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="afbed-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="afbed-218">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="afbed-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="afbed-219">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="afbed-219">**Sender domain**</span></span>
- <span data-ttu-id="afbed-220">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="afbed-220">**Subject**</span></span>
- <span data-ttu-id="afbed-221">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="afbed-221">**Submitted by**</span></span>
- <span data-ttu-id="afbed-222">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-222">**Submission type**</span></span>
- <span data-ttu-id="afbed-223">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="afbed-223">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="afbed-225">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="afbed-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="afbed-226">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="afbed-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="afbed-227">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="afbed-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="afbed-228">**Als** u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="afbed-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="afbed-229">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions** .</span><span class="sxs-lookup"><span data-stu-id="afbed-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions** .</span></span>

2. <span data-ttu-id="afbed-230">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="afbed-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="afbed-231">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="afbed-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="afbed-232">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="afbed-232">**Submitted on**</span></span>
- <span data-ttu-id="afbed-233">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-234">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-235">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="afbed-235">**Sender**</span></span>
- <span data-ttu-id="afbed-236">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="afbed-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="afbed-237">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="afbed-237">**Submission type**</span></span>

<span data-ttu-id="afbed-238">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="afbed-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="afbed-239">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="afbed-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="afbed-240">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="afbed-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="afbed-241">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="afbed-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="afbed-242">Gebruikers uitchecken ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="afbed-242">Undo user submissions</span></span>

<span data-ttu-id="afbed-243">Wanneer een gebruiker een verdacht e-mailbericht voor het aangepaste postvak heeft ingediend, beschikt de gebruiker en beheerder niet over de optie om de verzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="afbed-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="afbed-244">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="afbed-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="afbed-245">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="afbed-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="afbed-246">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="afbed-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="afbed-247">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="afbed-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="afbed-248">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="afbed-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="afbed-249">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="afbed-249">**Report clean**</span></span>
- <span data-ttu-id="afbed-250">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="afbed-250">**Report phishing**</span></span>
- <span data-ttu-id="afbed-251">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="afbed-251">**Report malware**</span></span>
- <span data-ttu-id="afbed-252">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="afbed-252">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
