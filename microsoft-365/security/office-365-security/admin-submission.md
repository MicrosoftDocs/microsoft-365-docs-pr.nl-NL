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
ms.openlocfilehash: 1ca1dc5e740aa5aa03a4c8b0c138eadb55c08a20
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844642"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="52ae0-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="52ae0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="52ae0-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="52ae0-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="52ae0-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="52ae0-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="52ae0-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="52ae0-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="52ae0-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="52ae0-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52ae0-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="52ae0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52ae0-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="52ae0-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="52ae0-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="52ae0-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="52ae0-111">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="52ae0-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="52ae0-112">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="52ae0-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="52ae0-113">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="52ae0-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="52ae0-114">Houd er rekening mee dat lidmaatschap van deze rollen groep is vereist voor [het weergeven van gebruikers inzendingen aan het aangepaste postvak](#view-user-submissions-to-the-custom-mailbox) , zoals verderop in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="52ae0-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="52ae0-115">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52ae0-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="52ae0-116">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="52ae0-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="52ae0-117">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions** , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="52ae0-118">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="52ae0-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="52ae0-119">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="52ae0-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="52ae0-120">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="52ae0-121">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="52ae0-122">**Netwerkbericht-id** : dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="52ae0-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="52ae0-123">**Bestand** : Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-123">**File** : Click **Choose file**.</span></span> <span data-ttu-id="52ae0-124">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="52ae0-125">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="52ae0-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="52ae0-126">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="52ae0-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="52ae0-127">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="52ae0-128">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="52ae0-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="52ae0-129">**Is geblokkeerd** : Selecteer **spam** , **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware**.</span></span> <span data-ttu-id="52ae0-130">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52ae0-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="52ae0-131">Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="52ae0-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="52ae0-132">Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="52ae0-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="52ae0-133">Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending.</span><span class="sxs-lookup"><span data-stu-id="52ae0-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="52ae0-134">Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict.</span><span class="sxs-lookup"><span data-stu-id="52ae0-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="52ae0-135">Opmerking op deze manier wordt de e-mail niet uitgevoerd via de Microsoft Defender for Office 365-stack volledig filteren, maar wordt een gedeeltelijke herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="52ae0-135">Note this does not run the email through the Microsoft Defender for Office 365 full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="52ae0-136">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-136">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="52ae0-138">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="52ae0-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="52ae0-139">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="52ae0-140">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="52ae0-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="52ae0-141">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="52ae0-142">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="52ae0-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="52ae0-143">**Moet zijn geblokkeerd** : Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-143">**Should have been blocked** : Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="52ae0-144">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-144">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="52ae0-146">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="52ae0-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="52ae0-147">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="52ae0-148">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-148">Click **Choose File**.</span></span> <span data-ttu-id="52ae0-149">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="52ae0-150">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="52ae0-151">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="52ae0-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="52ae0-152">Is **geblokkeerd** : **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="52ae0-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="52ae0-153">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-153">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="52ae0-155">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="52ae0-155">View admin submissions</span></span>

<span data-ttu-id="52ae0-156">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions** , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="52ae0-157">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="52ae0-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="52ae0-158">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="52ae0-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="52ae0-159">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="52ae0-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="52ae0-160">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="52ae0-160">**Sender**</span></span>
- <span data-ttu-id="52ae0-161">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="52ae0-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="52ae0-162">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="52ae0-162">**Submitted by**</span></span>
- <span data-ttu-id="52ae0-163">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-163">**Submission type**</span></span>
- <span data-ttu-id="52ae0-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="52ae0-164">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="52ae0-166">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="52ae0-167">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="52ae0-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="52ae0-168">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL** en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="52ae0-169">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="52ae0-169">View admin email submissions</span></span>

<span data-ttu-id="52ae0-170">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-170">Click the **Email** tab.</span></span>

<span data-ttu-id="52ae0-171">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="52ae0-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="52ae0-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="52ae0-172">**Date**</span></span>
- <span data-ttu-id="52ae0-173">**Ingediende id** : een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="52ae0-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="52ae0-174">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-175">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-176">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="52ae0-176">**Sender**</span></span>
- <span data-ttu-id="52ae0-177">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-178">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-178">**Submission type**</span></span>
- <span data-ttu-id="52ae0-179">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="52ae0-179">**Delivery reason**</span></span>
- <span data-ttu-id="52ae0-180">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-181">**Typebesturingselement**</span><span class="sxs-lookup"><span data-stu-id="52ae0-181">**Control type**</span></span>
- <span data-ttu-id="52ae0-182">**Besturingselementbron**</span><span class="sxs-lookup"><span data-stu-id="52ae0-182">**Control source**</span></span>

  <span data-ttu-id="52ae0-183"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="52ae0-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="52ae0-184">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="52ae0-184">View admin URL submissions</span></span>

<span data-ttu-id="52ae0-185">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-185">Click the **URL** tab.</span></span>

<span data-ttu-id="52ae0-186">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="52ae0-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="52ae0-187">**Datum**</span><span class="sxs-lookup"><span data-stu-id="52ae0-187">**Date**</span></span>
- <span data-ttu-id="52ae0-188">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="52ae0-188">**Submission ID**</span></span>
- <span data-ttu-id="52ae0-189">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-191">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-191">**Submission type**</span></span>
- <span data-ttu-id="52ae0-192">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="52ae0-193"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="52ae0-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="52ae0-194">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="52ae0-194">View admin attachment submissions</span></span>

<span data-ttu-id="52ae0-195">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="52ae0-196">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="52ae0-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="52ae0-197">**Datum**</span><span class="sxs-lookup"><span data-stu-id="52ae0-197">**Date**</span></span>
- <span data-ttu-id="52ae0-198">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="52ae0-198">**Submission ID**</span></span>
- <span data-ttu-id="52ae0-199">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-200">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-201">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-201">**Submission type**</span></span>
- <span data-ttu-id="52ae0-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="52ae0-203"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="52ae0-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="52ae0-204">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="52ae0-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="52ae0-205">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="52ae0-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="52ae0-206">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="52ae0-207">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="52ae0-208">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="52ae0-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="52ae0-209">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="52ae0-209">**Submitted on**</span></span>
- <span data-ttu-id="52ae0-210">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-211">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-212">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="52ae0-212">**Sender**</span></span>
- <span data-ttu-id="52ae0-213">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-214">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-214">**Submission type**</span></span>

<span data-ttu-id="52ae0-215"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="52ae0-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="52ae0-216">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="52ae0-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="52ae0-217">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="52ae0-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="52ae0-218">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="52ae0-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="52ae0-219">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="52ae0-219">**Sender domain**</span></span>
- <span data-ttu-id="52ae0-220">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="52ae0-220">**Subject**</span></span>
- <span data-ttu-id="52ae0-221">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="52ae0-221">**Submitted by**</span></span>
- <span data-ttu-id="52ae0-222">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-222">**Submission type**</span></span>
- <span data-ttu-id="52ae0-223">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="52ae0-223">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="52ae0-225">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="52ae0-226">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="52ae0-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="52ae0-227">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="52ae0-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="52ae0-228">**Als** u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="52ae0-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="52ae0-229">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="52ae0-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="52ae0-230">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="52ae0-231">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="52ae0-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="52ae0-232">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="52ae0-232">**Submitted on**</span></span>
- <span data-ttu-id="52ae0-233">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-234">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-235">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="52ae0-235">**Sender**</span></span>
- <span data-ttu-id="52ae0-236">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52ae0-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="52ae0-237">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="52ae0-237">**Submission type**</span></span>

<span data-ttu-id="52ae0-238">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="52ae0-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="52ae0-239">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="52ae0-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="52ae0-240">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="52ae0-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="52ae0-241">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="52ae0-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="52ae0-242">Gebruikers uitchecken ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="52ae0-242">Undo user submissions</span></span>

<span data-ttu-id="52ae0-243">Wanneer een gebruiker een verdacht e-mailbericht voor het aangepaste postvak heeft ingediend, beschikt de gebruiker en beheerder niet over de optie om de verzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="52ae0-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="52ae0-244">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="52ae0-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="52ae0-245">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="52ae0-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="52ae0-246">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="52ae0-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="52ae0-247">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="52ae0-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="52ae0-248">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="52ae0-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="52ae0-249">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="52ae0-249">**Report clean**</span></span>
- <span data-ttu-id="52ae0-250">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="52ae0-250">**Report phishing**</span></span>
- <span data-ttu-id="52ae0-251">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="52ae0-251">**Report malware**</span></span>
- <span data-ttu-id="52ae0-252">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="52ae0-252">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
