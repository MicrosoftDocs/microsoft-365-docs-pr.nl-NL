---
title: Admin-inzendingen
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
description: Beheerders kunnen informatie over het gebruik van de portal voor uitnodigingen van de beveiligings & nalevings centrum voor het verzenden van verdachte e-mailberichten, verdachte e-mailberichten, spam en andere mogelijk schadelijke berichten, Url's en bestanden aan Microsoft voor het scannen.
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577868"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="2cf8b-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="2cf8b-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="2cf8b-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="2cf8b-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="2cf8b-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2cf8b-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2cf8b-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2cf8b-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2cf8b-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="2cf8b-111">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="2cf8b-112">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2cf8b-113">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2cf8b-114">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="2cf8b-115">Voor alleen-lezen toegang tot de portal van ingediende items moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2cf8b-116">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2cf8b-117">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="2cf8b-118">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="2cf8b-119">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="2cf8b-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="2cf8b-120">Ga in het beveiligings & compliance naar beheerberichten voor **risicobeheer** door \> **geven** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="2cf8b-121">Op de pagina **items** die wordt weergegeven, klikt u op de knop **nieuwe aanvraag** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="2cf8b-122">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="2cf8b-123">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="2cf8b-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="2cf8b-124">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="2cf8b-125">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="2cf8b-126">**Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="2cf8b-127">**Bestand**: Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="2cf8b-128">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="2cf8b-129">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="2cf8b-130">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="2cf8b-131">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2cf8b-132">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2cf8b-133">**Is geblokkeerd**: Selecteer **spam**, **phishing**of **malware**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="2cf8b-134">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="2cf8b-135">Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="2cf8b-136">Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="2cf8b-137">Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="2cf8b-138">Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="2cf8b-139">Opmerking Hiermee wordt de e-mail niet uitgevoerd via de Office 365 ATP-stack voor volledig filteren, maar wordt een gedeeltelijk herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="2cf8b-140">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-140">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="2cf8b-142">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="2cf8b-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="2cf8b-143">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="2cf8b-144">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="2cf8b-145">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2cf8b-146">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2cf8b-147">**Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="2cf8b-148">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-148">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="2cf8b-150">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="2cf8b-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="2cf8b-151">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="2cf8b-152">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-152">Click **Choose File**.</span></span> <span data-ttu-id="2cf8b-153">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="2cf8b-154">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2cf8b-155">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2cf8b-156">Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="2cf8b-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="2cf8b-157">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-157">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="2cf8b-159">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="2cf8b-159">View admin submissions</span></span>

1. <span data-ttu-id="2cf8b-160">Ga in het beveiligings & compliance naar beheerberichten voor **risicobeheer** door \> **geven** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="2cf8b-161">Op de pagina **items** die wordt weergegeven, controleert u of het tabblad **beheerder submissies** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="2cf8b-162">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2cf8b-163">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2cf8b-164">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="2cf8b-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-165">**Sender**</span></span>
- <span data-ttu-id="2cf8b-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="2cf8b-167">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-167">**Submitted by**</span></span>
- <span data-ttu-id="2cf8b-168">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-168">**Submission type**</span></span>
- <span data-ttu-id="2cf8b-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-169">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="2cf8b-171">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2cf8b-172">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="2cf8b-173">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL**en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="2cf8b-174">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="2cf8b-174">View admin email submissions</span></span>

<span data-ttu-id="2cf8b-175">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-175">Click the **Email** tab.</span></span>

<span data-ttu-id="2cf8b-176">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2cf8b-177">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-177">**Date**</span></span>
- <span data-ttu-id="2cf8b-178">**Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="2cf8b-179">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-180">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-181">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-181">**Sender**</span></span>
- <span data-ttu-id="2cf8b-182">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-183">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-183">**Submission type**</span></span>
- <span data-ttu-id="2cf8b-184">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-184">**Delivery reason**</span></span>
- <span data-ttu-id="2cf8b-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-186">**Typebesturingselement**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-186">**Control type**</span></span>
- <span data-ttu-id="2cf8b-187">**Besturingselementbron**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-187">**Control source**</span></span>

  <span data-ttu-id="2cf8b-188"><sup>\*</sup>Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="2cf8b-189">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="2cf8b-189">View admin URL submissions</span></span>

<span data-ttu-id="2cf8b-190">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-190">Click the **URL** tab.</span></span>

<span data-ttu-id="2cf8b-191">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2cf8b-192">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-192">**Date**</span></span>
- <span data-ttu-id="2cf8b-193">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-193">**Submission ID**</span></span>
- <span data-ttu-id="2cf8b-194">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-196">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-196">**Submission type**</span></span>
- <span data-ttu-id="2cf8b-197">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2cf8b-198"><sup>\*</sup>Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="2cf8b-199">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="2cf8b-199">View admin attachment submissions</span></span>

<span data-ttu-id="2cf8b-200">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="2cf8b-201">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2cf8b-202">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-202">**Date**</span></span>
- <span data-ttu-id="2cf8b-203">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-203">**Submission ID**</span></span>
- <span data-ttu-id="2cf8b-204">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-205">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-206">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-206">**Submission type**</span></span>
- <span data-ttu-id="2cf8b-207">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2cf8b-208"><sup>\*</sup>Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="2cf8b-209">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="2cf8b-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="2cf8b-210">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="2cf8b-211">Ga in het beveiligings & compliance naar beheerberichten voor **risicobeheer** door \> **geven** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="2cf8b-212">Op de pagina **items** die wordt weergegeven, klikt u op het tabblad **gebruikers items** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="2cf8b-213">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2cf8b-214">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-214">**Submitted on**</span></span>
- <span data-ttu-id="2cf8b-215">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-216">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-217">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-217">**Sender**</span></span>
- <span data-ttu-id="2cf8b-218">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-219">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-219">**Submission type**</span></span>

<span data-ttu-id="2cf8b-220"><sup>\*</sup>Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="2cf8b-221">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2cf8b-222">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2cf8b-223">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="2cf8b-224">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-224">**Sender domain**</span></span>
- <span data-ttu-id="2cf8b-225">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-225">**Subject**</span></span>
- <span data-ttu-id="2cf8b-226">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-226">**Submitted by**</span></span>
- <span data-ttu-id="2cf8b-227">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-227">**Submission type**</span></span>
- <span data-ttu-id="2cf8b-228">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-228">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="2cf8b-230">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2cf8b-231">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="2cf8b-232">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="2cf8b-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="2cf8b-233">Als u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="2cf8b-234">Ga in het beveiligings & compliance naar beheerberichten voor **risicobeheer** door \> **geven** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="2cf8b-235">Op de pagina **items** die wordt weergegeven, klikt u op het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="2cf8b-236">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2cf8b-237">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-237">**Submitted on**</span></span>
- <span data-ttu-id="2cf8b-238">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-239">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-240">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-240">**Sender**</span></span>
- <span data-ttu-id="2cf8b-241">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cf8b-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2cf8b-242">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-242">**Submission type**</span></span>

<span data-ttu-id="2cf8b-243">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2cf8b-244">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2cf8b-245">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="2cf8b-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2cf8b-246">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="2cf8b-247">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="2cf8b-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="2cf8b-248">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="2cf8b-249">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="2cf8b-250">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="2cf8b-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="2cf8b-251">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-251">**Report clean**</span></span>
- <span data-ttu-id="2cf8b-252">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-252">**Report phishing**</span></span>
- <span data-ttu-id="2cf8b-253">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-253">**Report malware**</span></span>
- <span data-ttu-id="2cf8b-254">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="2cf8b-254">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
