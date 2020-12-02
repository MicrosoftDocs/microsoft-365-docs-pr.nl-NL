---
title: Admin-inzendingen
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: 1e133c0d4a875fc9735cc8a92e42b6ffeee6dd5f
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527743"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3ad26-103">Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="3ad26-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3ad26-104">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.</span><span class="sxs-lookup"><span data-stu-id="3ad26-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3ad26-105">Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="3ad26-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="3ad26-106">Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).</span><span class="sxs-lookup"><span data-stu-id="3ad26-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="3ad26-107">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="3ad26-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ad26-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="3ad26-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ad26-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3ad26-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3ad26-110">Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="3ad26-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3ad26-111">Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:</span><span class="sxs-lookup"><span data-stu-id="3ad26-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3ad26-112">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3ad26-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="3ad26-113">**Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3ad26-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="3ad26-114">Houd er rekening mee dat lidmaatschap van deze rollen groep is vereist voor [het weergeven van gebruikers inzendingen aan het aangepaste postvak](#view-user-submissions-to-the-custom-mailbox) , zoals verderop in dit onderwerp wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="3ad26-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="3ad26-115">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ad26-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3ad26-116">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ad26-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3ad26-117">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="3ad26-118">Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="3ad26-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3ad26-119">Een dubieuze e-mail naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="3ad26-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3ad26-120">Selecteer in de sectie **object type** de optie **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3ad26-121">Gebruik een van de volgende opties in de sectie **opmaak van indiening** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3ad26-122">**Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="3ad26-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="3ad26-123">**Bestand**: Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="3ad26-124">In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="3ad26-125">Beheerders met Defender voor Office 365, abonnement 1 of abonnement 2 kunnen berichten indienen als oud als 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="3ad26-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="3ad26-126">Andere beheerders kunnen 7 dagen maar één keer teruggaan.</span><span class="sxs-lookup"><span data-stu-id="3ad26-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="3ad26-127">Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3ad26-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3ad26-128">Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="3ad26-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3ad26-129">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ad26-130">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="3ad26-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ad26-131">**Is geblokkeerd**: Selecteer **spam**, **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="3ad26-132">Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3ad26-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3ad26-133">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-133">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3ad26-135">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="3ad26-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3ad26-136">Selecteer in de sectie **object type** de optie **URL**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3ad26-137">Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="3ad26-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="3ad26-138">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ad26-139">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="3ad26-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ad26-140">**Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3ad26-141">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-141">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3ad26-143">Een verdacht bestand bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="3ad26-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3ad26-144">Selecteer in de sectie **object type** de optie **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3ad26-145">Klik op **bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-145">Click **Choose File**.</span></span> <span data-ttu-id="3ad26-146">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3ad26-147">Selecteer een van de volgende opties in de sectie **reden voor indiening** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3ad26-148">**Mag niet zijn geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="3ad26-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3ad26-149">Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...</span><span class="sxs-lookup"><span data-stu-id="3ad26-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3ad26-150">Wanneer u klaar bent, klikt u op de knop **verzenden** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-150">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="3ad26-152">Beheerders inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="3ad26-152">View admin submissions</span></span>

<span data-ttu-id="3ad26-153">Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3ad26-154">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ad26-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ad26-155">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="3ad26-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ad26-156">Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3ad26-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3ad26-157">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="3ad26-157">**Sender**</span></span>
- <span data-ttu-id="3ad26-158">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="3ad26-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3ad26-159">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="3ad26-159">**Submitted by**</span></span>
- <span data-ttu-id="3ad26-160">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-160">**Submission type**</span></span>
- <span data-ttu-id="3ad26-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="3ad26-161">**Status**</span></span>

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3ad26-163">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ad26-164">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3ad26-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3ad26-165">Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL** en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3ad26-166">E-mail inzendingen van de beheerder weergeven</span><span class="sxs-lookup"><span data-stu-id="3ad26-166">View admin email submissions</span></span>

<span data-ttu-id="3ad26-167">Selecteer het tabblad **e-mail** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-167">Click the **Email** tab.</span></span>

<span data-ttu-id="3ad26-168">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="3ad26-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ad26-169">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3ad26-169">**Date**</span></span>
- <span data-ttu-id="3ad26-170">**Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.</span><span class="sxs-lookup"><span data-stu-id="3ad26-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3ad26-171">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-172">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-173">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="3ad26-173">**Sender**</span></span>
- <span data-ttu-id="3ad26-174">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-175">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-175">**Submission type**</span></span>
- <span data-ttu-id="3ad26-176">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="3ad26-176">**Delivery reason**</span></span>
- <span data-ttu-id="3ad26-177">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ad26-178"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3ad26-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="3ad26-179">Details van opnieuw gescande beheerder</span><span class="sxs-lookup"><span data-stu-id="3ad26-179">Admin submission rescan details</span></span>

<span data-ttu-id="3ad26-180">Berichten die worden verzonden in admin-inzendingen, worden opnieuw gecontroleerd en de resultaten worden weergegeven in het detail menu:</span><span class="sxs-lookup"><span data-stu-id="3ad26-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="3ad26-181">Wanneer de e-mail verificatie van de afzender mislukt op het moment van de levering.</span><span class="sxs-lookup"><span data-stu-id="3ad26-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="3ad26-182">Informatie over beleids hits die de verdict van een bericht kunnen beïnvloeden of van de overschreven.</span><span class="sxs-lookup"><span data-stu-id="3ad26-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="3ad26-183">Actuele detonatie resultaten om te zien of de Url's of bestanden in het bericht schadelijk of niet waren.</span><span class="sxs-lookup"><span data-stu-id="3ad26-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="3ad26-184">Feedback van Beoordelingen.</span><span class="sxs-lookup"><span data-stu-id="3ad26-184">Feedback from graders.</span></span>

<span data-ttu-id="3ad26-185">Als er een overschrijving is gevonden, moet de herscan in enkele minuten voltooien.</span><span class="sxs-lookup"><span data-stu-id="3ad26-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="3ad26-186">Als er geen fout is opgetreden bij het verifiëren van e-mailberichten of als de bezorging geen invloed heeft op de ontvangst van een override, kan de feedback van een cijfer een dag duren.</span><span class="sxs-lookup"><span data-stu-id="3ad26-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3ad26-187">Ingediende items van de beheerders-URL weergeven</span><span class="sxs-lookup"><span data-stu-id="3ad26-187">View admin URL submissions</span></span>

<span data-ttu-id="3ad26-188">Klik op het tabblad **URL** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-188">Click the **URL** tab.</span></span>

<span data-ttu-id="3ad26-189">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="3ad26-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ad26-190">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3ad26-190">**Date**</span></span>
- <span data-ttu-id="3ad26-191">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="3ad26-191">**Submission ID**</span></span>
- <span data-ttu-id="3ad26-192">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-194">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-194">**Submission type**</span></span>
- <span data-ttu-id="3ad26-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ad26-196"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3ad26-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3ad26-197">Ingediende beheerders bijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="3ad26-197">View admin attachment submissions</span></span>

<span data-ttu-id="3ad26-198">Klik op het tabblad **bijlagen** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3ad26-199">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="3ad26-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ad26-200">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3ad26-200">**Date**</span></span>
- <span data-ttu-id="3ad26-201">**Verzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="3ad26-201">**Submission ID**</span></span>
- <span data-ttu-id="3ad26-202">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-203">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-204">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-204">**Submission type**</span></span>
- <span data-ttu-id="3ad26-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3ad26-206"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3ad26-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3ad26-207">Naar Microsoft verzonden gebruikers inzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="3ad26-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="3ad26-208">Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.</span><span class="sxs-lookup"><span data-stu-id="3ad26-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3ad26-209">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3ad26-210">Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3ad26-211">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="3ad26-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ad26-212">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="3ad26-212">**Submitted on**</span></span>
- <span data-ttu-id="3ad26-213">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-214">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-215">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="3ad26-215">**Sender**</span></span>
- <span data-ttu-id="3ad26-216">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-217">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-217">**Submission type**</span></span>

<span data-ttu-id="3ad26-218"><sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="3ad26-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3ad26-219">Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ad26-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ad26-220">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="3ad26-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ad26-221">Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3ad26-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3ad26-222">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="3ad26-222">**Sender domain**</span></span>
- <span data-ttu-id="3ad26-223">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="3ad26-223">**Subject**</span></span>
- <span data-ttu-id="3ad26-224">**Verzonden door**</span><span class="sxs-lookup"><span data-stu-id="3ad26-224">**Submitted by**</span></span>
- <span data-ttu-id="3ad26-225">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-225">**Submission type**</span></span>
- <span data-ttu-id="3ad26-226">**IP van afzender**</span><span class="sxs-lookup"><span data-stu-id="3ad26-226">**Sender IP**</span></span>

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3ad26-228">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ad26-229">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3ad26-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3ad26-230">Gebruikers inzendingen weergeven voor het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="3ad26-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3ad26-231">**Als** u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.</span><span class="sxs-lookup"><span data-stu-id="3ad26-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3ad26-232">Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="3ad26-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3ad26-233">Selecteer het tabblad **aangepast postvak** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3ad26-234">U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="3ad26-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3ad26-235">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="3ad26-235">**Submitted on**</span></span>
- <span data-ttu-id="3ad26-236">**Verzonden door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-237">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-238">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="3ad26-238">**Sender**</span></span>
- <span data-ttu-id="3ad26-239">**IP van afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3ad26-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3ad26-240">**Type levering**</span><span class="sxs-lookup"><span data-stu-id="3ad26-240">**Submission type**</span></span>

<span data-ttu-id="3ad26-241">Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3ad26-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3ad26-242">U kunt meerdere waarden opgeven, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="3ad26-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3ad26-243">Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen** van de **grafiek** .</span><span class="sxs-lookup"><span data-stu-id="3ad26-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3ad26-244">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3ad26-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="3ad26-245">Gebruikers uitchecken ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="3ad26-245">Undo user submissions</span></span>

<span data-ttu-id="3ad26-246">Wanneer een gebruiker een verdacht e-mailbericht voor het aangepaste postvak heeft ingediend, beschikt de gebruiker en beheerder niet over de optie om de verzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="3ad26-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="3ad26-247">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="3ad26-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3ad26-248">Berichten indienen bij Microsoft vanuit het aangepaste Postvak</span><span class="sxs-lookup"><span data-stu-id="3ad26-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3ad26-249">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden.</span><span class="sxs-lookup"><span data-stu-id="3ad26-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3ad26-250">Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.</span><span class="sxs-lookup"><span data-stu-id="3ad26-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3ad26-251">Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:</span><span class="sxs-lookup"><span data-stu-id="3ad26-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3ad26-252">**Rapport opschonen**</span><span class="sxs-lookup"><span data-stu-id="3ad26-252">**Report clean**</span></span>
- <span data-ttu-id="3ad26-253">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="3ad26-253">**Report phishing**</span></span>
- <span data-ttu-id="3ad26-254">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="3ad26-254">**Report malware**</span></span>
- <span data-ttu-id="3ad26-255">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="3ad26-255">**Report spam**</span></span>

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
