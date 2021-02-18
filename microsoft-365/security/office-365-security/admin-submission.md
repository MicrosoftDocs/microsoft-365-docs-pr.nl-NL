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
description: Beheerders kunnen in het beveiligings &- en compliancecentrum voor het verzenden van verdachte e-mailberichten, verdachte phishing-e-mailberichten, spam en andere mogelijk schadelijke berichten, URL's en bestanden naar Microsoft verzenden om te scannen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288787"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="ffb53-103">Inzending door beheerder gebruiken om verdachte spam, phish, URL's en bestanden bij Microsoft in te dienen</span><span class="sxs-lookup"><span data-stu-id="ffb53-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ffb53-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ffb53-104">**Applies to**</span></span>
- [<span data-ttu-id="ffb53-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ffb53-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ffb53-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ffb53-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="ffb53-107">In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Voor indieningen in het beveiligings &- en compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft te verzenden om te scannen.</span><span class="sxs-lookup"><span data-stu-id="ffb53-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="ffb53-108">Wanneer u een e-mailbericht indient, krijgt u:</span><span class="sxs-lookup"><span data-stu-id="ffb53-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="ffb53-109">**Controle van e-mailverificatie:** Details over het al dan niet doorgegeven of mislukt van de e-mailverificatie toen deze werd geleverd.</span><span class="sxs-lookup"><span data-stu-id="ffb53-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="ffb53-110">**Beleidstreffers:** informatie over beleid dat inkomende e-mail in uw tenant mogelijk heeft toegestaan of geblokkeerd, en het overschrijven van onze servicefilters.</span><span class="sxs-lookup"><span data-stu-id="ffb53-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="ffb53-111">**Nettoladingsreput/detonatie:** Onderzoek van eventuele URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="ffb53-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="ffb53-112">**Cijferanalyse:** beoordeling door beoordelingsbeoordelingen om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="ffb53-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffb53-113">De nettoladings-/detonatie- en cijferanalyse worden niet in alle tenants uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ffb53-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="ffb53-114">Informatie wordt geblokkeerd voor het verlaten van de organisatie wanneer gegevens de tenantgrens niet mogen verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="ffb53-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="ffb53-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ffb53-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ffb53-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ffb53-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ffb53-117">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ffb53-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ffb53-118">Als u rechtstreeks naar de **inzendingspagina wilt** gaan, gebruikt u <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="ffb53-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="ffb53-119">Als u berichten en bestanden wilt verzenden bij Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="ffb53-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="ffb53-120">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ffb53-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="ffb53-121">**Organisatiebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="ffb53-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="ffb53-122">Houd er rekening mee dat lidmaatschap van deze rollengroep is vereist om [gebruikersinzendingen voor](#view-user-submissions-to-the-custom-mailbox) het aangepaste postvak weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="ffb53-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="ffb53-123">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen [verzenden bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ffb53-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="ffb53-124">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffb53-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="ffb53-125">Ga in het & compliancecentrum naar  Inzendingen voor risicobeheer, controleer of u zich op het tabblad Voor het indienen van beheerders hebt weergegeven en klik vervolgens op \>  **Nieuwe inzending.** </span><span class="sxs-lookup"><span data-stu-id="ffb53-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="ffb53-126">Gebruik **de flyout** Nieuwe inzending die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="ffb53-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="ffb53-127">Een twijfelachtig e-mailbericht naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="ffb53-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="ffb53-128">Selecteer **E-mail in** de sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="ffb53-129">Gebruik in **de sectie Indeling** voor inzending een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="ffb53-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="ffb53-130">Netwerkbericht-id: dit is een GUID-waarde die beschikbaar is in de kop **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **kop X-MS-Office365-Filtering-Correlation-Id** in berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="ffb53-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="ffb53-131">**Bestand:** klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="ffb53-132">Zoek en selecteer het EML- of MSG-bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ffb53-133">Beheerders met Defender voor Office 365-abonnement 1 of Abonnement 2 kunnen berichten verzenden die dertig dagen oud zijn.</span><span class="sxs-lookup"><span data-stu-id="ffb53-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="ffb53-134">Andere beheerders kunnen slechts zeven dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="ffb53-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="ffb53-135">Geef in **de sectie Ontvangers** een of meer geadresseerden op voor wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ffb53-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="ffb53-136">Met de beleidscontrole wordt bepaald of scannen van e-mail is overgeslagen vanwege het beleid van de gebruiker of organisatie.</span><span class="sxs-lookup"><span data-stu-id="ffb53-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="ffb53-137">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="ffb53-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ffb53-138">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="ffb53-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ffb53-139">**Zou geblokkeerd moeten zijn:** **Spam,** **Phishing** of **Malware selecteren.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="ffb53-140">Als u het niet zeker weet, moet u dit goed doen.</span><span class="sxs-lookup"><span data-stu-id="ffb53-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="ffb53-141">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="ffb53-141">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="ffb53-143">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="ffb53-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="ffb53-144">Selecteer URL **in de** sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="ffb53-145">Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="ffb53-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="ffb53-146">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="ffb53-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ffb53-147">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="ffb53-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ffb53-148">**Zou geblokkeerd moeten zijn:** Selecteer **Phishing** of **Malware.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="ffb53-149">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="ffb53-149">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="ffb53-151">Een mogelijk bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffb53-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="ffb53-152">Selecteer Bijlage **in de** sectie **Objecttype.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="ffb53-153">Klik **op Bestand kiezen.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-153">Click **Choose File**.</span></span> <span data-ttu-id="ffb53-154">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="ffb53-155">Selecteer een **van de volgende opties in** de sectie Reden voor inzending:</span><span class="sxs-lookup"><span data-stu-id="ffb53-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ffb53-156">**Was niet geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="ffb53-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ffb53-157">**Zou geblokkeerd moeten zijn:** **Malware** is de enige optie en wordt automatisch geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ffb53-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="ffb53-158">Klik op de knop Verzenden wanneer u **klaar** bent.</span><span class="sxs-lookup"><span data-stu-id="ffb53-158">When you're finished, click the **Submit** button.</span></span>

   ![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="ffb53-160">Inzendingen van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-160">View admin submissions</span></span>

<span data-ttu-id="ffb53-161">Ga in het & compliancecentrum naar  Inzendingen voor risicobeheer, controleer of u zich op het tabblad Voor het indienen van beheerders hebt weergegeven en klik vervolgens op \>  **Nieuwe inzending.** </span><span class="sxs-lookup"><span data-stu-id="ffb53-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ffb53-162">Boven aan de pagina kunt u een begindatum en einddatum invoeren en **(standaard)** filteren op Indiening-id (een GUID-waarde die is toegewezen aan elke inzending) door een waarde in het vak in te voeren en op de knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="ffb53-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ffb53-163">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="ffb53-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ffb53-164">Als u de filtercriteria wilt wijzigen, klikt u op **de knop Id** van indiening en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="ffb53-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="ffb53-165">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ffb53-165">**Sender**</span></span>
- <span data-ttu-id="ffb53-166">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="ffb53-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="ffb53-167">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="ffb53-167">**Submitted by**</span></span>
- <span data-ttu-id="ffb53-168">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-168">**Submission type**</span></span>
- <span data-ttu-id="ffb53-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="ffb53-169">**Status**</span></span>

![Filteropties voor inzendingen door beheerders](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="ffb53-171">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ffb53-172">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffb53-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="ffb53-173">Onder de grafiek ziet u drie tabbladen: **E-mail** (standaard), **URL** en **Bijlage.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="ffb53-174">E-mailinzendingen van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-174">View admin email submissions</span></span>

<span data-ttu-id="ffb53-175">Klik op het **tabblad E-mail.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-175">Click the **Email** tab.</span></span>

<span data-ttu-id="ffb53-176">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="ffb53-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ffb53-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ffb53-177">**Date**</span></span>
- <span data-ttu-id="ffb53-178">**Indienings-id:** een GUID-waarde die is toegewezen aan elke inzending.</span><span class="sxs-lookup"><span data-stu-id="ffb53-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="ffb53-179">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-180">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-181">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ffb53-181">**Sender**</span></span>
- <span data-ttu-id="ffb53-182">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-183">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-183">**Submission type**</span></span>
- <span data-ttu-id="ffb53-184">**Bezorgings reden**</span><span class="sxs-lookup"><span data-stu-id="ffb53-184">**Delivery reason**</span></span>
- <span data-ttu-id="ffb53-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ffb53-186"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="ffb53-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="ffb53-187">Rescandegegevens voor inzending door beheerder</span><span class="sxs-lookup"><span data-stu-id="ffb53-187">Admin submission rescan details</span></span>

<span data-ttu-id="ffb53-188">Berichten die worden ingediend in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de details van de flyout:</span><span class="sxs-lookup"><span data-stu-id="ffb53-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="ffb53-189">Als er een fout is geweest in de e-mailverificatie van de afzender op het moment van bezorging.</span><span class="sxs-lookup"><span data-stu-id="ffb53-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="ffb53-190">Informatie over beleidstreffers die mogelijk van invloed kunnen zijn op of de uitspraak van een bericht hebben overgenomen.</span><span class="sxs-lookup"><span data-stu-id="ffb53-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="ffb53-191">De huidige detonatieresultaten om te zien of de URL's of bestanden in het bericht schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="ffb53-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="ffb53-192">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="ffb53-192">Feedback from graders.</span></span>

<span data-ttu-id="ffb53-193">Als een overschrijven is gevonden, zou het opnieuw scannen binnen enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="ffb53-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="ffb53-194">Als er geen probleem is met e-mailverificatie of bezorging niet is beïnvloed door een overschrijven, kan het geven van feedback van cijferaars tot een dag duren.</span><span class="sxs-lookup"><span data-stu-id="ffb53-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="ffb53-195">Url-inzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-195">View admin URL submissions</span></span>

<span data-ttu-id="ffb53-196">Klik op het **tabblad URL.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-196">Click the **URL** tab.</span></span>

<span data-ttu-id="ffb53-197">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="ffb53-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ffb53-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ffb53-198">**Date**</span></span>
- <span data-ttu-id="ffb53-199">**Indienings-id**</span><span class="sxs-lookup"><span data-stu-id="ffb53-199">**Submission ID**</span></span>
- <span data-ttu-id="ffb53-200">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-202">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-202">**Submission type**</span></span>
- <span data-ttu-id="ffb53-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ffb53-204"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="ffb53-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="ffb53-205">Inzendingen voor bijlagen van beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-205">View admin attachment submissions</span></span>

<span data-ttu-id="ffb53-206">Klik op **het tabblad** Bijlagen.</span><span class="sxs-lookup"><span data-stu-id="ffb53-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="ffb53-207">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="ffb53-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ffb53-208">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ffb53-208">**Date**</span></span>
- <span data-ttu-id="ffb53-209">**Indienings-id**</span><span class="sxs-lookup"><span data-stu-id="ffb53-209">**Submission ID**</span></span>
- <span data-ttu-id="ffb53-210">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-211">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-212">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-212">**Submission type**</span></span>
- <span data-ttu-id="ffb53-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ffb53-214"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="ffb53-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="ffb53-215">Gebruikersinzendingen voor Microsoft weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="ffb53-216">Als u de invoegversie Bericht rapporteren, [de invoegversie](enable-the-report-message-add-in.md) [Voor](enable-the-report-phish-add-in.md)phishing melden hebt geïmplementeerd of als mensen de [ingebouwde](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapportage in de webversie van Outlook gebruiken, kunt u zien wat gebruikers melden op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="ffb53-217">Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ffb53-218">Selecteer het **tabblad Gebruikersinzendingen** en klik op **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ffb53-219">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="ffb53-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ffb53-220">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="ffb53-220">**Submitted on**</span></span>
- <span data-ttu-id="ffb53-221">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-222">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-223">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ffb53-223">**Sender**</span></span>
- <span data-ttu-id="ffb53-224">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-225">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-225">**Submission type**</span></span>

<span data-ttu-id="ffb53-226"><sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="ffb53-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="ffb53-227">Boven aan de pagina kunt u een begindatum en einddatum invoeren en (standaard) filteren op afzender door een waarde in het vak in te voeren en op de knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="ffb53-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ffb53-228">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="ffb53-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ffb53-229">Als u de filtercriteria wilt wijzigen, klikt u op **de knop Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="ffb53-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="ffb53-230">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="ffb53-230">**Sender domain**</span></span>
- <span data-ttu-id="ffb53-231">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="ffb53-231">**Subject**</span></span>
- <span data-ttu-id="ffb53-232">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="ffb53-232">**Submitted by**</span></span>
- <span data-ttu-id="ffb53-233">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-233">**Submission type**</span></span>
- <span data-ttu-id="ffb53-234">**AFZENDER-IP**</span><span class="sxs-lookup"><span data-stu-id="ffb53-234">**Sender IP**</span></span>

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="ffb53-236">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ffb53-237">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffb53-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="ffb53-238">Gebruikersinzendingen voor het aangepaste postvak weergeven</span><span class="sxs-lookup"><span data-stu-id="ffb53-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="ffb53-239">**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd voor het ontvangen van door de gebruiker gerapporteerde berichten, kunt u berichten bekijken en verzenden die zijn bezorgd in het postvak van de rapportage.</span><span class="sxs-lookup"><span data-stu-id="ffb53-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="ffb53-240">Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ffb53-241">Selecteer het **tabblad Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="ffb53-242">U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:</span><span class="sxs-lookup"><span data-stu-id="ffb53-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ffb53-243">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="ffb53-243">**Submitted on**</span></span>
- <span data-ttu-id="ffb53-244">**Ingediend door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-245">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-246">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="ffb53-246">**Sender**</span></span>
- <span data-ttu-id="ffb53-247">**AFZENDER-IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffb53-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ffb53-248">**Type indiening**</span><span class="sxs-lookup"><span data-stu-id="ffb53-248">**Submission type**</span></span>

<span data-ttu-id="ffb53-249">Boven aan de pagina kunt u een begindatum en einddatum invoeren  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op de knop Vernieuwen ![ te ](../../media/scc-quarantine-refresh.png) klikken.</span><span class="sxs-lookup"><span data-stu-id="ffb53-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ffb53-250">U kunt meerdere waarden invoeren, gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="ffb53-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ffb53-251">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.**</span><span class="sxs-lookup"><span data-stu-id="ffb53-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ffb53-252">Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ffb53-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="ffb53-253">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="ffb53-253">Undo user submissions</span></span>

<span data-ttu-id="ffb53-254">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak indient, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="ffb53-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="ffb53-255">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ffb53-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="ffb53-256">Berichten naar Microsoft verzenden vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="ffb53-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="ffb53-257">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft verzenden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="ffb53-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="ffb53-258">Hiermee wordt een gebruikersinzending op effectieve wijze verplaatst naar een inzending door een beheerder.</span><span class="sxs-lookup"><span data-stu-id="ffb53-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="ffb53-259">Selecteer op **het tabblad** Aangepast postvak een  bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="ffb53-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="ffb53-260">**Rapport opschoont**</span><span class="sxs-lookup"><span data-stu-id="ffb53-260">**Report clean**</span></span>
- <span data-ttu-id="ffb53-261">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="ffb53-261">**Report phishing**</span></span>
- <span data-ttu-id="ffb53-262">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="ffb53-262">**Report malware**</span></span>
- <span data-ttu-id="ffb53-263">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="ffb53-263">**Report spam**</span></span>

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
