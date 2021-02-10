---
title: Inzendingen door beheerders
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
description: Beheerders kunnen in het beveiligings- en compliancecentrum van het beveiligings-&-compliancecentrum verdachte e-mailberichten, verdachte phishing-e-mailberichten, spam en andere mogelijk schadelijke berichten, URL's en bestanden voor scannen naar Microsoft verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7a822909c318cb336c179b299aa64cd71dcca4d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175869"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="51666-103">Inzending door beheerder gebruiken om verdachte spam, phish, URL's en bestanden bij Microsoft in te dienen</span><span class="sxs-lookup"><span data-stu-id="51666-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="51666-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="51666-104">**Applies to**</span></span>
- [<span data-ttu-id="51666-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="51666-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="51666-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="51666-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)


<span data-ttu-id="51666-107">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Voorzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft te verzenden om te scannen.</span><span class="sxs-lookup"><span data-stu-id="51666-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="51666-108">Wanneer u een e-mailbericht indient, krijgt u:</span><span class="sxs-lookup"><span data-stu-id="51666-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="51666-109">**Controle van e-mailverificatie:** Details over het al dan niet doorgegeven of mislukt van de e-mailverificatie toen deze werd geleverd.</span><span class="sxs-lookup"><span data-stu-id="51666-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="51666-110">**Beleidstreffers:** informatie over beleid dat inkomende e-mail in uw tenant mogelijk heeft toegestaan of geblokkeerd, waardoor onze servicefilters worden overschrijven.</span><span class="sxs-lookup"><span data-stu-id="51666-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="51666-111">**Nettoladingsreput/detonatie:** Onderzoek van eventuele URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="51666-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="51666-112">**Cijferanalyse:** beoordeling door beoordelingsbeoordelingen om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="51666-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51666-113">De nettoladings-/detonatie- en cijferanalyse worden niet in alle tenants uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="51666-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="51666-114">Informatie wordt geblokkeerd voor het verlaten van de organisatie wanneer gegevens de tenantgrens niet mogen verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="51666-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="51666-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="51666-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51666-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="51666-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51666-117">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="51666-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="51666-118">Als u rechtstreeks naar de **inzendingspagina wilt** gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="51666-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="51666-119">Als u berichten en bestanden wilt verzenden bij Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="51666-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="51666-120">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="51666-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="51666-121">**Organisatiebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="51666-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="51666-122">Houd er rekening mee dat lidmaatschap van deze rollengroep is vereist om [gebruikersinzendingen voor](#view-user-submissions-to-the-custom-mailbox) het aangepaste postvak weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="51666-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="51666-123">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen [verzenden bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="51666-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="51666-124">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="51666-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="51666-125">Ga in het & compliancecentrum naar  Inzendingen voor \> **bedreigingsbeheer,** controleer of u zich op het tabblad **Admin-inzendingen** vindt en klik vervolgens op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="51666-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="51666-126">Gebruik **de flyout** Nieuwe inzending die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="51666-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="51666-127">Een twijfelachtig e-mailbericht naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="51666-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="51666-128">Selecteer **E-mail in** de sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="51666-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="51666-129">Gebruik in **de sectie Indeling** voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="51666-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="51666-130">Netwerkbericht-id: dit is een GUID-waarde die beschikbaar is in de kop **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **kop X-MS-Office365-Filtering-Correlation-Id** in berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="51666-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="51666-131">**Bestand:** klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="51666-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="51666-132">Zoek en selecteer het EML- of MSG-bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="51666-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="51666-133">Beheerders met Defender voor Office 365-abonnement 1 of Abonnement 2 kunnen berichten verzenden die dertig dagen oud zijn.</span><span class="sxs-lookup"><span data-stu-id="51666-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="51666-134">Andere beheerders kunnen slechts zeven dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="51666-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="51666-135">Geef in **de sectie Ontvangers** een of meer geadresseerden op voor wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="51666-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="51666-136">Met de beleidscontrole wordt bepaald of scannen van e-mail is overgeslagen vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="51666-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="51666-137">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="51666-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="51666-138">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="51666-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="51666-139">**Zou geblokkeerd moeten zijn:** **Spam,** **Phishing** of **Malware selecteren.**</span><span class="sxs-lookup"><span data-stu-id="51666-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="51666-140">Als u het niet zeker weet, moet u dit goed doen.</span><span class="sxs-lookup"><span data-stu-id="51666-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="51666-141">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="51666-141">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="51666-143">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="51666-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="51666-144">Selecteer URL **in de** sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="51666-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="51666-145">Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="51666-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="51666-146">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="51666-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="51666-147">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="51666-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="51666-148">**Zou geblokkeerd moeten zijn:** Selecteer **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="51666-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="51666-149">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="51666-149">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="51666-151">Een verdacht bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="51666-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="51666-152">Selecteer Bijlage **in de** sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="51666-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="51666-153">Klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="51666-153">Click **Choose File**.</span></span> <span data-ttu-id="51666-154">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="51666-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="51666-155">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="51666-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="51666-156">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="51666-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="51666-157">**Zou geblokkeerd moeten zijn:** **Malware** is de enige optie en wordt automatisch geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="51666-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="51666-158">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="51666-158">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="51666-160">Inzendingen van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-160">View admin submissions</span></span>

<span data-ttu-id="51666-161">Ga in het & compliancecentrum naar  Inzendingen voor \> **bedreigingsbeheer,** controleer of u zich op het tabblad **Admin-inzendingen** vindt en klik vervolgens op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="51666-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="51666-162">Boven aan de pagina kunt u een begindatum en einddatum invoeren en **(standaard)** u kunt filteren op Indiening-id (een GUID-waarde die is toegewezen aan elke inzending) door een waarde in het vak in te voeren en op de knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="51666-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="51666-163">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="51666-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="51666-164">Als u de filtercriteria wilt wijzigen, klikt u op **de knop Id** van indiening en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="51666-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="51666-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="51666-165">**Sender**</span></span>
- <span data-ttu-id="51666-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="51666-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="51666-167">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="51666-167">**Submitted by**</span></span>
- <span data-ttu-id="51666-168">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-168">**Submission type**</span></span>
- <span data-ttu-id="51666-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="51666-169">**Status**</span></span>

![Filteropties voor inzendingen door beheerders](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="51666-171">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="51666-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="51666-172">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51666-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="51666-173">Onder de grafiek ziet u drie tabbladen: **E-mail** (standaard), **URL** en **Bijlage.**</span><span class="sxs-lookup"><span data-stu-id="51666-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="51666-174">E-mailinzendingen van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-174">View admin email submissions</span></span>

<span data-ttu-id="51666-175">Klik op het **tabblad E-mail.**</span><span class="sxs-lookup"><span data-stu-id="51666-175">Click the **Email** tab.</span></span>

<span data-ttu-id="51666-176">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="51666-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="51666-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="51666-177">**Date**</span></span>
- <span data-ttu-id="51666-178">**Indienings-id:** een GUID-waarde die is toegewezen aan elke inzending.</span><span class="sxs-lookup"><span data-stu-id="51666-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="51666-179">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-180">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-181">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="51666-181">**Sender**</span></span>
- <span data-ttu-id="51666-182">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-183">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-183">**Submission type**</span></span>
- <span data-ttu-id="51666-184">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="51666-184">**Delivery reason**</span></span>
- <span data-ttu-id="51666-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="51666-186"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="51666-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="51666-187">Rescandetails voor inzending door beheerder</span><span class="sxs-lookup"><span data-stu-id="51666-187">Admin submission rescan details</span></span>

<span data-ttu-id="51666-188">Berichten die worden ingediend in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de details van de flyout:</span><span class="sxs-lookup"><span data-stu-id="51666-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="51666-189">Als er een fout is geweest in de e-mailverificatie van de afzender op het moment van bezorging.</span><span class="sxs-lookup"><span data-stu-id="51666-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="51666-190">Informatie over beleidstreffers die invloed kunnen hebben op of overschrijven van het bericht.</span><span class="sxs-lookup"><span data-stu-id="51666-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="51666-191">De huidige detonatieresultaten om te zien of de URL's of bestanden in het bericht schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="51666-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="51666-192">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="51666-192">Feedback from graders.</span></span>

<span data-ttu-id="51666-193">Als een overschrijven is gevonden, zou het opnieuw scannen binnen enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="51666-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="51666-194">Als er geen probleem is met e-mailverificatie of bezorging niet is beïnvloed door een overschrijven, kan de feedback van cijferaars tot een dag duren.</span><span class="sxs-lookup"><span data-stu-id="51666-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="51666-195">Url-inzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-195">View admin URL submissions</span></span>

<span data-ttu-id="51666-196">Klik op het **tabblad URL.**</span><span class="sxs-lookup"><span data-stu-id="51666-196">Click the **URL** tab.</span></span>

<span data-ttu-id="51666-197">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="51666-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="51666-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="51666-198">**Date**</span></span>
- <span data-ttu-id="51666-199">**Inzendings-id**</span><span class="sxs-lookup"><span data-stu-id="51666-199">**Submission ID**</span></span>
- <span data-ttu-id="51666-200">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-202">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-202">**Submission type**</span></span>
- <span data-ttu-id="51666-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="51666-204"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="51666-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="51666-205">Inzendingen voor beheerdersbijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-205">View admin attachment submissions</span></span>

<span data-ttu-id="51666-206">Klik op **het tabblad** Bijlagen.</span><span class="sxs-lookup"><span data-stu-id="51666-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="51666-207">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="51666-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="51666-208">**Datum**</span><span class="sxs-lookup"><span data-stu-id="51666-208">**Date**</span></span>
- <span data-ttu-id="51666-209">**Inzendings-id**</span><span class="sxs-lookup"><span data-stu-id="51666-209">**Submission ID**</span></span>
- <span data-ttu-id="51666-210">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-211">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-212">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-212">**Submission type**</span></span>
- <span data-ttu-id="51666-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="51666-214"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="51666-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="51666-215">Gebruikersinzendingen voor Microsoft weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="51666-216">Als u de invoegversie Bericht rapporteren, [de invoegversie](enable-the-report-message-add-in.md) [Voor](enable-the-report-phish-add-in.md)phishing melden hebt geïmplementeerd of als mensen de [ingebouwde](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapportage in de webversie van Outlook gebruiken, kunt u zien wat gebruikers melden op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="51666-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="51666-217">Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**</span><span class="sxs-lookup"><span data-stu-id="51666-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="51666-218">Selecteer het **tabblad Gebruikersinzendingen** en klik op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="51666-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="51666-219">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="51666-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="51666-220">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="51666-220">**Submitted on**</span></span>
- <span data-ttu-id="51666-221">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-222">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-223">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="51666-223">**Sender**</span></span>
- <span data-ttu-id="51666-224">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-225">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-225">**Submission type**</span></span>

<span data-ttu-id="51666-226"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="51666-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="51666-227">Boven aan de pagina kunt u een begindatum en einddatum invoeren en (standaard) filteren op afzender door een waarde in het vak in te voeren en op de knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="51666-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="51666-228">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="51666-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="51666-229">Als u de filtercriteria wilt wijzigen, klikt u op **de knop Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="51666-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="51666-230">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="51666-230">**Sender domain**</span></span>
- <span data-ttu-id="51666-231">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="51666-231">**Subject**</span></span>
- <span data-ttu-id="51666-232">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="51666-232">**Submitted by**</span></span>
- <span data-ttu-id="51666-233">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-233">**Submission type**</span></span>
- <span data-ttu-id="51666-234">**AFZENDER-IP**</span><span class="sxs-lookup"><span data-stu-id="51666-234">**Sender IP**</span></span>

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="51666-236">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="51666-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="51666-237">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51666-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="51666-238">Gebruikersinzendingen voor het aangepaste postvak weergeven</span><span class="sxs-lookup"><span data-stu-id="51666-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="51666-239">**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd voor het ontvangen van door de gebruiker gerapporteerde berichten, kunt u berichten bekijken en verzenden die zijn bezorgd in het postvak van de rapportage.</span><span class="sxs-lookup"><span data-stu-id="51666-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="51666-240">Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**</span><span class="sxs-lookup"><span data-stu-id="51666-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="51666-241">Selecteer het **tabblad Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="51666-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="51666-242">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="51666-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="51666-243">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="51666-243">**Submitted on**</span></span>
- <span data-ttu-id="51666-244">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-245">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-246">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="51666-246">**Sender**</span></span>
- <span data-ttu-id="51666-247">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51666-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="51666-248">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="51666-248">**Submission type**</span></span>

<span data-ttu-id="51666-249">Boven aan de pagina kunt u een begindatum en einddatum invoeren  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op de knop Vernieuwen ![ te ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="51666-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="51666-250">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="51666-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="51666-251">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="51666-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="51666-252">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51666-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="51666-253">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="51666-253">Undo user submissions</span></span>

<span data-ttu-id="51666-254">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak indient, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="51666-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="51666-255">Als de gebruiker de e-mail wil herstellen, kan deze worden hersteld in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="51666-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="51666-256">Berichten naar Microsoft verzenden vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="51666-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="51666-257">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft verzenden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="51666-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="51666-258">Hiermee wordt een gebruikersinzending op effectieve wijze verplaatst naar een inzending door een beheerder.</span><span class="sxs-lookup"><span data-stu-id="51666-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="51666-259">Selecteer op **het tabblad** Aangepast postvak een  bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="51666-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="51666-260">**Rapport opschoont**</span><span class="sxs-lookup"><span data-stu-id="51666-260">**Report clean**</span></span>
- <span data-ttu-id="51666-261">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="51666-261">**Report phishing**</span></span>
- <span data-ttu-id="51666-262">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="51666-262">**Report malware**</span></span>
- <span data-ttu-id="51666-263">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="51666-263">**Report spam**</span></span>

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
