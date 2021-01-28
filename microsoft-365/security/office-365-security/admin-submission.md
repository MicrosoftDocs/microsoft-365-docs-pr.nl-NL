---
title: Admin-inzendingen
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
description: Beheerders kunnen informatie over het gebruik van de portal voor uitnodigingen van de beveiligings & nalevings centrum voor het verzenden van verdachte e-mailberichten, verdachte e-mailberichten, spam en andere mogelijk schadelijke berichten, Url's en bestanden aan Microsoft voor het scannen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029512"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="4c256-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="4c256-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="4c256-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="4c256-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="4c256-105">Wanneer u een e-mailbericht verzendt, krijgt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="4c256-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="4c256-106">**Verificatie via e-mail verificatie**: Details over of het doorgeven van e-mail verificatie is gelukt of mislukt.</span><span class="sxs-lookup"><span data-stu-id="4c256-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="4c256-107">**Beleids hits**: informatie over beleidsregels die de inkomende e-mail in uw Tenant mogelijk hebben toegestaan of geblokkeerd, waarbij de Verdicts van het servicefilter wordt overschreven.</span><span class="sxs-lookup"><span data-stu-id="4c256-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="4c256-108">**Reputatie/detonatie van nettolading**: onderzoek van url's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="4c256-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="4c256-109">**Grader analyse**: Bekijk de gevolgde voor menselijke kwaliteiten om te bevestigen of berichten al dan niet schadelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="4c256-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c256-110">Nettolading van de reputatie/detonatie en van de proefbaan worden niet in alle tenants geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="4c256-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="4c256-111">De gegevens worden geblokkeerd wanneer u de gegevens van de Tenant niet hoeft te laten voldoen.</span><span class="sxs-lookup"><span data-stu-id="4c256-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="4c256-112">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="4c256-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4c256-113">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="4c256-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4c256-114">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4c256-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4c256-115">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="4c256-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="4c256-116">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="4c256-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="4c256-117">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4c256-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="4c256-118">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4c256-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="4c256-119">Houd er rekening mee dat lidmaatschap van deze rollen groep is vereist voor [het weergeven van gebruikers inzendingen voor het aangepaste postvak](#view-user-submissions-to-the-custom-mailbox) , zoals verderop in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="4c256-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="4c256-120">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c256-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="4c256-121">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c256-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="4c256-122">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="4c256-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="4c256-123">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="4c256-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="4c256-124">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="4c256-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="4c256-125">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="4c256-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="4c256-126">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="4c256-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="4c256-127">**Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **x-MS-Exchange-Organization-Network-Message-ID** in het bericht of in de header **X-MS-Office365-filtering-correlatie-id** in berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="4c256-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="4c256-128">**Bestand**: Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="4c256-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="4c256-129">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="4c256-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c256-130">Beheerders met Defender voor Office 365, abonnement 1 of abonnement 2 kunnen berichten indienen als oud als 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="4c256-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="4c256-131">Andere beheerders kunnen 7 dagen maar één keer teruggaan.</span><span class="sxs-lookup"><span data-stu-id="4c256-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="4c256-132">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4c256-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="4c256-133">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="4c256-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="4c256-134">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="4c256-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4c256-135">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="4c256-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4c256-136">**Is geblokkeerd**: Selecteer **spam**, **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="4c256-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="4c256-137">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4c256-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="4c256-138">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="4c256-138">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="4c256-140">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="4c256-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="4c256-141">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="4c256-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="4c256-142">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="4c256-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="4c256-143">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="4c256-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4c256-144">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="4c256-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4c256-145">**Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="4c256-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="4c256-146">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="4c256-146">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="4c256-148">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="4c256-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="4c256-149">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="4c256-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="4c256-150">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="4c256-150">Click **Choose File**.</span></span> <span data-ttu-id="4c256-151">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="4c256-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="4c256-152">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="4c256-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4c256-153">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="4c256-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4c256-154">Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="4c256-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="4c256-155">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="4c256-155">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="4c256-157">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="4c256-157">View admin submissions</span></span>

<span data-ttu-id="4c256-158">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> , ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="4c256-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="4c256-159">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4c256-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4c256-160">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="4c256-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4c256-161">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="4c256-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="4c256-162">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="4c256-162">**Sender**</span></span>
- <span data-ttu-id="4c256-163">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="4c256-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="4c256-164">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="4c256-164">**Submitted by**</span></span>
- <span data-ttu-id="4c256-165">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-165">**Submission type**</span></span>
- <span data-ttu-id="4c256-166">**Status**</span><span class="sxs-lookup"><span data-stu-id="4c256-166">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="4c256-168">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="4c256-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4c256-169">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4c256-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="4c256-170">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL** en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="4c256-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="4c256-171">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="4c256-171">View admin email submissions</span></span>

<span data-ttu-id="4c256-172">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="4c256-172">Click the **Email** tab.</span></span>

<span data-ttu-id="4c256-173">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="4c256-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4c256-174">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c256-174">**Date**</span></span>
- <span data-ttu-id="4c256-175">**Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="4c256-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="4c256-176">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-177">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-178">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="4c256-178">**Sender**</span></span>
- <span data-ttu-id="4c256-179">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-180">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-180">**Submission type**</span></span>
- <span data-ttu-id="4c256-181">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="4c256-181">**Delivery reason**</span></span>
- <span data-ttu-id="4c256-182">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4c256-183"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="4c256-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="4c256-184">Details van opnieuw gescande beheerder</span><span class="sxs-lookup"><span data-stu-id="4c256-184">Admin submission rescan details</span></span>

<span data-ttu-id="4c256-185">Berichten die worden verzonden in admin-inzendingen, worden opnieuw gecontroleerd en de resultaten worden weergegeven in het detail menu:</span><span class="sxs-lookup"><span data-stu-id="4c256-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="4c256-186">Wanneer de e-mail verificatie van de afzender mislukt op het moment van de levering.</span><span class="sxs-lookup"><span data-stu-id="4c256-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="4c256-187">Informatie over beleids hits die de verdict van een bericht kunnen beïnvloeden of van de overschreven.</span><span class="sxs-lookup"><span data-stu-id="4c256-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="4c256-188">Actuele detonatie resultaten om te zien of de Url's of bestanden in het bericht schadelijk of niet waren.</span><span class="sxs-lookup"><span data-stu-id="4c256-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="4c256-189">Feedback van Beoordelingen.</span><span class="sxs-lookup"><span data-stu-id="4c256-189">Feedback from graders.</span></span>

<span data-ttu-id="4c256-190">Als er een overschrijving is gevonden, moet de herscan in enkele minuten voltooien.</span><span class="sxs-lookup"><span data-stu-id="4c256-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="4c256-191">Als er geen fout is opgetreden bij het verifiëren van e-mailberichten of als de bezorging geen invloed heeft op de ontvangst van een override, kan de feedback van een cijfer een dag duren.</span><span class="sxs-lookup"><span data-stu-id="4c256-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="4c256-192">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="4c256-192">View admin URL submissions</span></span>

<span data-ttu-id="4c256-193">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="4c256-193">Click the **URL** tab.</span></span>

<span data-ttu-id="4c256-194">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="4c256-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4c256-195">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c256-195">**Date**</span></span>
- <span data-ttu-id="4c256-196">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="4c256-196">**Submission ID**</span></span>
- <span data-ttu-id="4c256-197">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-199">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-199">**Submission type**</span></span>
- <span data-ttu-id="4c256-200">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4c256-201"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="4c256-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="4c256-202">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="4c256-202">View admin attachment submissions</span></span>

<span data-ttu-id="4c256-203">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="4c256-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="4c256-204">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="4c256-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4c256-205">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4c256-205">**Date**</span></span>
- <span data-ttu-id="4c256-206">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="4c256-206">**Submission ID**</span></span>
- <span data-ttu-id="4c256-207">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-208">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-209">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-209">**Submission type**</span></span>
- <span data-ttu-id="4c256-210">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4c256-211"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="4c256-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="4c256-212">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="4c256-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="4c256-213">Als u de invoegtoepassing [voor het rapporteren van berichten](enable-the-report-message-add-in.md)hebt geïmplementeerd, de [phishing-](enable-the-report-phish-add-in.md)uitbreiding voor het rapport of gebruikers de [ingebouwde rapporten in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)gebruiken, kunt u zien welke gebruikers rapporteren op het tabblad **gebruikers submissies** .</span><span class="sxs-lookup"><span data-stu-id="4c256-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="4c256-214">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> .</span><span class="sxs-lookup"><span data-stu-id="4c256-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="4c256-215">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.</span><span class="sxs-lookup"><span data-stu-id="4c256-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="4c256-216">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="4c256-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4c256-217">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="4c256-217">**Submitted on**</span></span>
- <span data-ttu-id="4c256-218">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-219">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-220">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="4c256-220">**Sender**</span></span>
- <span data-ttu-id="4c256-221">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-222">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-222">**Submission type**</span></span>

<span data-ttu-id="4c256-223"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="4c256-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="4c256-224">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4c256-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4c256-225">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="4c256-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4c256-226">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="4c256-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="4c256-227">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="4c256-227">**Sender domain**</span></span>
- <span data-ttu-id="4c256-228">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="4c256-228">**Subject**</span></span>
- <span data-ttu-id="4c256-229">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="4c256-229">**Submitted by**</span></span>
- <span data-ttu-id="4c256-230">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-230">**Submission type**</span></span>
- <span data-ttu-id="4c256-231">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="4c256-231">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="4c256-233">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="4c256-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4c256-234">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4c256-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="4c256-235">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="4c256-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="4c256-236">**Als** u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="4c256-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="4c256-237">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> .</span><span class="sxs-lookup"><span data-stu-id="4c256-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="4c256-238">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="4c256-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="4c256-239">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="4c256-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4c256-240">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="4c256-240">**Submitted on**</span></span>
- <span data-ttu-id="4c256-241">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-242">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-243">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="4c256-243">**Sender**</span></span>
- <span data-ttu-id="4c256-244">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4c256-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4c256-245">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="4c256-245">**Submission type**</span></span>

<span data-ttu-id="4c256-246">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4c256-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4c256-247">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="4c256-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4c256-248">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="4c256-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4c256-249">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4c256-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="4c256-250">Gebruikers uitchecken ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="4c256-250">Undo user submissions</span></span>

<span data-ttu-id="4c256-251">Wanneer een gebruiker een verdacht e-mailbericht voor het aangepaste postvak heeft ingediend, beschikt de gebruiker en beheerder niet over de optie om de verzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="4c256-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="4c256-252">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="4c256-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="4c256-253">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="4c256-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="4c256-254">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="4c256-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="4c256-255">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="4c256-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="4c256-256">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="4c256-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="4c256-257">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="4c256-257">**Report clean**</span></span>
- <span data-ttu-id="4c256-258">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="4c256-258">**Report phishing**</span></span>
- <span data-ttu-id="4c256-259">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="4c256-259">**Report malware**</span></span>
- <span data-ttu-id="4c256-260">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="4c256-260">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
