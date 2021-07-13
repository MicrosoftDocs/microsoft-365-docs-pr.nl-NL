---
title: Beheerdersinzendingen
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
description: Beheerders kunnen leren hoe ze de portal Inzendingen in de Microsoft 365 Defender-portal kunnen gebruiken om verdachte e-mailberichten, vermoedelijke phishingmails, spam en andere potentieel schadelijke berichten, URL's en e-mailbijlagen bij Microsoft in te dienen voor het opnieuw controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d18dd7f5dc702f08a722652394aeb0102f100ef
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409054"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="47738-103">Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden</span><span class="sxs-lookup"><span data-stu-id="47738-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47738-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="47738-104">**Applies to**</span></span>
- [<span data-ttu-id="47738-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="47738-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47738-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="47738-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="47738-107">In Microsoft 365 organisaties met Exchange Online-postvakken kunnen beheerders de portal Inzendingen in de Microsoft 365 Defender-portal gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.</span><span class="sxs-lookup"><span data-stu-id="47738-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="47738-108">Wanneer u een e-mailbericht indient, krijgt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="47738-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="47738-109">**Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="47738-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="47738-110">**Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.</span><span class="sxs-lookup"><span data-stu-id="47738-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="47738-111">**Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="47738-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="47738-112">**Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="47738-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47738-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span><span class="sxs-lookup"><span data-stu-id="47738-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="47738-114">Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="47738-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="47738-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="47738-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47738-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="47738-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47738-117">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="47738-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="47738-118">Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="47738-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="47738-119">Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="47738-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="47738-120">**Organisatiebeheer** of **Beveiligingslezer** in de [Microsoft 365 Defender portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="47738-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="47738-121">Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-microsoft) weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="47738-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="47738-122">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="47738-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="47738-123">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="47738-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="47738-124">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="47738-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="47738-125">Controleer op **de pagina Inzendingen** of het tabblad Ingediend voor analyse is geselecteerd en klik vervolgens op  ![ Advertentiepictogram Verzenden bij Microsoft voor ](../../media/m365-cc-sc-create-icon.png) **analyse.**</span><span class="sxs-lookup"><span data-stu-id="47738-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="47738-126">Gebruik de **flyout Verzenden bij Microsoft** voor controle die wordt weergegeven om het bericht, de URL of de e-mailbijlage in te dienen, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="47738-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47738-127">Bestands- en URL-inzendingen zijn niet beschikbaar in de clouds die niet toestaan dat gegevens de omgeving verlaten.</span><span class="sxs-lookup"><span data-stu-id="47738-127">File and URL submissions are not available in the clouds that do not allow for data to leave the environment.</span></span> <span data-ttu-id="47738-128">De mogelijkheid om Bestand of URL te selecteren, wordt grijs weergegeven.</span><span class="sxs-lookup"><span data-stu-id="47738-128">The ability to select File or URL will be greyed out.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="47738-129">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="47738-129">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="47738-130">Controleer in **het vak Selecteer het inzendingstype** of **E-mail** is geselecteerd in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="47738-130">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="47738-131">Gebruik een van de volgende opties in de sectie **Netwerkbericht-id toevoegen** of het e-mailbestand uploaden:</span><span class="sxs-lookup"><span data-stu-id="47738-131">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="47738-132">**De** e-mailnetwerkbericht-id toevoegen: dit is een GUID-waarde die beschikbaar is in de koptekst **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="47738-132">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="47738-133">**Upload het e-mailbestand (.msg of .eml)**: Klik op **Bestanden bladeren.**</span><span class="sxs-lookup"><span data-stu-id="47738-133">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="47738-134">Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="47738-134">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="47738-135">De mogelijkheid om berichten zo oud als 30 dagen in te dienen, is tijdelijk opgeschort voor Defender voor Office 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="47738-135">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="47738-136">Beheerders kunnen slechts 7 dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="47738-136">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="47738-137">Geef in **het vak Kies een geadresseerde met een probleem** de geadresseerde op tegen wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="47738-137">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="47738-138">Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="47738-138">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="47738-139">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="47738-139">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="47738-140">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="47738-140">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="47738-141">**Moet zijn geblokkeerd:** Selecteer  een van de volgende waarden (als u het niet zeker weet, gebruik uw beste beoordeling) in de sectie Het e-mailbericht moet zijn gecategoriseerd als sectie die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="47738-141">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="47738-142">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="47738-142">**Phish**</span></span>
     - <span data-ttu-id="47738-143">**Spam**</span><span class="sxs-lookup"><span data-stu-id="47738-143">**Spam**</span></span>
     - <span data-ttu-id="47738-144">**Malware**</span><span class="sxs-lookup"><span data-stu-id="47738-144">**Malware**</span></span>

5. <span data-ttu-id="47738-145">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="47738-145">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="47738-146">![Voorbeeld van nieuwe URL-inzending](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="47738-146">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="47738-147">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="47738-147">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="47738-148">Selecteer url in de vervolgkeuzelijst **in** het vak Selecteer het inzendingstype. </span><span class="sxs-lookup"><span data-stu-id="47738-148">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="47738-149">Voer in het vak **URL** dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="47738-149">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="47738-150">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="47738-150">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="47738-151">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="47738-151">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="47738-152">**Moet zijn geblokkeerd:** Selecteer **Phish** of Malware in de sectie Deze **URL** moet zijn gecategoriseerd als sectie die wordt **weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="47738-152">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="47738-153">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="47738-153">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="47738-154">![Voorbeeld van nieuwe e-mailinzending](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="47738-154">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="47738-155">Een verdachte e-mailbijlage indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="47738-155">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="47738-156">Selecteer bestand in de vervolgkeuzelijst in het vak Selecteer het  **inzendingstype.**</span><span class="sxs-lookup"><span data-stu-id="47738-156">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="47738-157">Klik in **de** sectie Bestand die wordt weergegeven op **Bestanden bladeren.**</span><span class="sxs-lookup"><span data-stu-id="47738-157">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="47738-158">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="47738-158">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="47738-159">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="47738-159">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="47738-160">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="47738-160">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="47738-161">**Moet zijn geblokkeerd:** In de deze **URL** moet zijn gecategoriseerd als sectie die wordt weergegeven, **Malware** is de enige keuze en wordt automatisch geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="47738-161">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="47738-162">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="47738-162">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="47738-163">![Voorbeeld van nieuwe bijlageinzending](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="47738-163">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="47738-164">Beheerdersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="47738-164">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="47738-165">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="47738-165">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="47738-166">Controleer op **de pagina Inzendingen** of het tabblad **Ingediend voor analyse** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="47738-166">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="47738-167">U kunt de items sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="47738-167">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="47738-168">Klik **op Kolommen aanpassen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="47738-168">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="47738-169">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="47738-169">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="47738-170">**Inzendingsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-170">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-171">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-171">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-172">**Verzonden datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-172">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-173">**Inzendingstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-173">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-174">**Reden voor het indienen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-174">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-175">**Status opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-175">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-176">**Resultaat opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-176">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-177">**Filter-uitspraak**</span><span class="sxs-lookup"><span data-stu-id="47738-177">**Filter verdict**</span></span>
     - <span data-ttu-id="47738-178">**Reden voor bezorging/blokkering**</span><span class="sxs-lookup"><span data-stu-id="47738-178">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="47738-179">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="47738-179">**Submission ID**</span></span>
     - <span data-ttu-id="47738-180">**Netwerkbericht-id/object-id**</span><span class="sxs-lookup"><span data-stu-id="47738-180">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="47738-181">**Richting**</span><span class="sxs-lookup"><span data-stu-id="47738-181">**Direction**</span></span>
     - <span data-ttu-id="47738-182">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="47738-182">**Sender IP**</span></span>
     - <span data-ttu-id="47738-183">**Bulk compliant level (BCL)**</span><span class="sxs-lookup"><span data-stu-id="47738-183">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="47738-184">**Destination**</span><span class="sxs-lookup"><span data-stu-id="47738-184">**Destination**</span></span>
     - <span data-ttu-id="47738-185">**Beleidsactie**</span><span class="sxs-lookup"><span data-stu-id="47738-185">**Policy action**</span></span>
     - <span data-ttu-id="47738-186">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="47738-186">**Submitted by**</span></span>

     <span data-ttu-id="47738-187">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="47738-187">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="47738-188">Als u de items wilt filteren, klikt u op **Filteren.**</span><span class="sxs-lookup"><span data-stu-id="47738-188">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="47738-189">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="47738-189">The available filters are:</span></span>
     - <span data-ttu-id="47738-190">**Verzonden datum**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="47738-190">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="47738-191">**Inzendingstype:** **E-mail,** **URL** of **Bestand.**</span><span class="sxs-lookup"><span data-stu-id="47738-191">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="47738-192">**Inzending-id:** een GUID-waarde die aan elke inzending is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="47738-192">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="47738-193">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="47738-193">**Network Message ID**</span></span>
     - <span data-ttu-id="47738-194">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="47738-194">**Sender**</span></span>

     <span data-ttu-id="47738-195">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="47738-195">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="47738-196">![Nieuwe filteropties voor beheerdersinzendingen](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="47738-196">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="47738-197">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="47738-197">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="47738-198">**Geen**</span><span class="sxs-lookup"><span data-stu-id="47738-198">**None**</span></span>
     - <span data-ttu-id="47738-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="47738-199">**Type**</span></span>
     - <span data-ttu-id="47738-200">**Reden**</span><span class="sxs-lookup"><span data-stu-id="47738-200">**Reason**</span></span>
     - <span data-ttu-id="47738-201">**Status**</span><span class="sxs-lookup"><span data-stu-id="47738-201">**Status**</span></span>
     - <span data-ttu-id="47738-202">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="47738-202">**Rescan result**</span></span>

   - <span data-ttu-id="47738-203">Als u de items wilt exporteren, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="47738-203">To export the entries, click **Export**.</span></span> <span data-ttu-id="47738-204">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="47738-204">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="47738-205">Details van de inzending van beheerders opnieuw scannen</span><span class="sxs-lookup"><span data-stu-id="47738-205">Admin submission rescan details</span></span>

<span data-ttu-id="47738-206">Berichten die worden verzonden in beheerdersinzendingen, worden beoordeeld en de resultaten worden weergegeven in de flyout details van de inzendingen:</span><span class="sxs-lookup"><span data-stu-id="47738-206">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="47738-207">Of er tijdens de levering een fout zat in de e-mailverificatie van de afzender.</span><span class="sxs-lookup"><span data-stu-id="47738-207">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="47738-208">Informatie over eventuele beleidstreffers die het oordeel over een bericht kunnen hebben beïnvloed of overschreven.</span><span class="sxs-lookup"><span data-stu-id="47738-208">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="47738-209">Huidige deactiveringsresultaten om te zien of de URL's of bestanden in het bericht schadelijk waren of niet.</span><span class="sxs-lookup"><span data-stu-id="47738-209">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="47738-210">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="47738-210">Feedback from graders.</span></span>

<span data-ttu-id="47738-211">Als een overschrijving is gevonden, zou het opnieuw scannen in enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="47738-211">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="47738-212">Als er geen probleem was bij e-mailverificatie of bezorging werd niet beïnvloed door een overschrijven, kan de feedback van cijferaars maximaal een dag duren.</span><span class="sxs-lookup"><span data-stu-id="47738-212">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="47738-213">Gebruikersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="47738-213">View user submissions to Microsoft</span></span>

<span data-ttu-id="47738-214">Als u de invoegvoeging Rapportbericht , de [invoeging](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)melden of personen de [ingebouwde](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapportage in webversie van Outlook hebt  geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Bericht van gebruiker gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="47738-214">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="47738-215">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="47738-215">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="47738-216">Selecteer op **de pagina Inzendingen** het tabblad **Gerapporteerde berichten van gebruiker.**</span><span class="sxs-lookup"><span data-stu-id="47738-216">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="47738-217">U kunt de items sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="47738-217">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="47738-218">Klik **op Kolommen aanpassen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="47738-218">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="47738-219">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="47738-219">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="47738-220">**Onderwerp e-mail**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-220">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-221">**Gerapporteerd door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-221">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-222">**Datum gerapporteerd**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-222">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-223">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-223">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-224">**Gerapporteerde reden**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-224">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-225">**Resultaat opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47738-225">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="47738-226">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="47738-226">**Message reported ID**</span></span>
     - <span data-ttu-id="47738-227">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="47738-227">**Network Message ID**</span></span>
     - <span data-ttu-id="47738-228">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="47738-228">**Sender IP**</span></span>
     - <span data-ttu-id="47738-229">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="47738-229">**Phish simulation**</span></span>

     <span data-ttu-id="47738-230">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="47738-230">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="47738-231">Als u de items wilt filteren, klikt u op **Filteren.**</span><span class="sxs-lookup"><span data-stu-id="47738-231">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="47738-232">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="47738-232">The available filters are:</span></span>
     - <span data-ttu-id="47738-233">**Datum gerapporteerd**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="47738-233">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="47738-234">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="47738-234">**Reported by**</span></span>
     - <span data-ttu-id="47738-235">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="47738-235">**Email subject**</span></span>
     - <span data-ttu-id="47738-236">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="47738-236">**Message reported ID**</span></span>
     - <span data-ttu-id="47738-237">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="47738-237">**Network Message ID**</span></span>
     - <span data-ttu-id="47738-238">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="47738-238">**Sender**</span></span>
     - <span data-ttu-id="47738-239">**Gerapporteerde reden:** **Geen ongewenste** e-mail, **Phish** of **Spam.**</span><span class="sxs-lookup"><span data-stu-id="47738-239">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="47738-240">**Phish-simulatie:** **Ja** of **Nee**</span><span class="sxs-lookup"><span data-stu-id="47738-240">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="47738-241">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="47738-241">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="47738-242">![Nieuwe filteropties voor gebruikersinzendingen](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="47738-242">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="47738-243">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="47738-243">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="47738-244">**Geen**</span><span class="sxs-lookup"><span data-stu-id="47738-244">**None**</span></span>
     - <span data-ttu-id="47738-245">**Reden**</span><span class="sxs-lookup"><span data-stu-id="47738-245">**Reason**</span></span>
     - <span data-ttu-id="47738-246">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="47738-246">**Sender**</span></span>
     - <span data-ttu-id="47738-247">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="47738-247">**Reported by**</span></span>
     - <span data-ttu-id="47738-248">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="47738-248">**Rescan result**</span></span>
     - <span data-ttu-id="47738-249">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="47738-249">**Phish simulation**</span></span>

   - <span data-ttu-id="47738-250">Als u de items wilt exporteren, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="47738-250">To export the entries, click **Export**.</span></span> <span data-ttu-id="47738-251">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="47738-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="47738-252">Als organisaties zijn geconfigureerd om alleen gerapporteerde berichten van gebruikers naar het aangepaste postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in **door** de gebruiker gerapporteerde berichten altijd leeg.</span><span class="sxs-lookup"><span data-stu-id="47738-252">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="47738-253">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="47738-253">Undo user submissions</span></span>

<span data-ttu-id="47738-254">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="47738-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="47738-255">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="47738-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="47738-256">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="47738-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="47738-257">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="47738-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="47738-258">Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.</span><span class="sxs-lookup"><span data-stu-id="47738-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="47738-259">Selecteer op **het tabblad Gerapporteerde** berichten van gebruiker een bericht in de lijst, klik op Verzenden bij **Microsoft** voor analyse en selecteer vervolgens een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="47738-259">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="47738-260">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="47738-260">**Report clean**</span></span>
- <span data-ttu-id="47738-261">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="47738-261">**Report phishing**</span></span>
- <span data-ttu-id="47738-262">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="47738-262">**Report malware**</span></span>
- <span data-ttu-id="47738-263">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="47738-263">**Report spam**</span></span>
- <span data-ttu-id="47738-264">**Onderzoek starten**</span><span class="sxs-lookup"><span data-stu-id="47738-264">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="47738-265">![Nieuwe opties op de knop Actie](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="47738-265">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
