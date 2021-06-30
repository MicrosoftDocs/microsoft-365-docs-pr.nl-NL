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
ms.openlocfilehash: eecb635972be85e1a1a4f95c2786f209ee249745
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203278"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="a5a77-103">Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden</span><span class="sxs-lookup"><span data-stu-id="a5a77-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a5a77-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="a5a77-104">**Applies to**</span></span>
- [<span data-ttu-id="a5a77-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a5a77-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a5a77-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a5a77-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="a5a77-107">In Microsoft 365 organisaties met Exchange Online-postvakken kunnen beheerders de portal Inzendingen in de Microsoft 365 Defender-portal gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.</span><span class="sxs-lookup"><span data-stu-id="a5a77-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="a5a77-108">Wanneer u een e-mailbericht indient, krijgt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="a5a77-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="a5a77-109">**Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="a5a77-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="a5a77-110">**Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.</span><span class="sxs-lookup"><span data-stu-id="a5a77-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="a5a77-111">**Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="a5a77-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="a5a77-112">**Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="a5a77-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5a77-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span><span class="sxs-lookup"><span data-stu-id="a5a77-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="a5a77-114">Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="a5a77-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="a5a77-115">Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a5a77-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a5a77-116">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="a5a77-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a5a77-117">U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="a5a77-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a5a77-118">Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="a5a77-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="a5a77-119">Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:</span><span class="sxs-lookup"><span data-stu-id="a5a77-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="a5a77-120">**Organisatiebeheer** of **Beveiligingslezer** in de [Microsoft 365 Defender portal.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="a5a77-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="a5a77-121">Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-microsoft) weer te geven, zoals verder wordt beschreven in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="a5a77-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="a5a77-122">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a5a77-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="a5a77-123">Verdachte inhoud rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5a77-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="a5a77-124">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a5a77-125">Controleer op **de pagina Inzendingen** of het tabblad Ingediend voor analyse is geselecteerd en klik vervolgens op  ![ Advertentiepictogram Verzenden bij Microsoft voor ](../../media/m365-cc-sc-create-icon.png) **analyse.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="a5a77-126">Gebruik de **flyout Verzenden bij Microsoft** voor controle die wordt weergegeven om het bericht, de URL of de e-mailbijlage in te dienen, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="a5a77-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="a5a77-127">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5a77-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="a5a77-128">Controleer in **het vak Selecteer het inzendingstype** of **E-mail** is geselecteerd in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="a5a77-128">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="a5a77-129">Gebruik een van de volgende opties in de sectie **Netwerkbericht-id toevoegen** of het e-mailbestand uploaden:</span><span class="sxs-lookup"><span data-stu-id="a5a77-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="a5a77-130">**De** e-mailnetwerkbericht-id toevoegen: dit is een GUID-waarde die beschikbaar is in de koptekst **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="a5a77-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="a5a77-131">**Upload het e-mailbestand (.msg of .eml)**: Klik op **Bestanden bladeren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-131">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="a5a77-132">Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a5a77-133">De mogelijkheid om berichten zo oud als 30 dagen in te dienen, is tijdelijk opgeschort voor Defender voor Office 365 klanten.</span><span class="sxs-lookup"><span data-stu-id="a5a77-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="a5a77-134">Beheerders kunnen slechts 7 dagen teruggaan.</span><span class="sxs-lookup"><span data-stu-id="a5a77-134">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="a5a77-135">Geef in **het vak Kies een geadresseerde met een probleem** de geadresseerde op tegen wie u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a5a77-135">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="a5a77-136">Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="a5a77-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="a5a77-137">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a5a77-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a5a77-138">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="a5a77-138">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a5a77-139">**Moet zijn geblokkeerd:** Selecteer  een van de volgende waarden (als u het niet zeker weet, gebruik uw beste beoordeling) in de sectie Het e-mailbericht moet zijn gecategoriseerd als sectie die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a5a77-139">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="a5a77-140">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="a5a77-140">**Phish**</span></span>
     - <span data-ttu-id="a5a77-141">**Spam**</span><span class="sxs-lookup"><span data-stu-id="a5a77-141">**Spam**</span></span>
     - <span data-ttu-id="a5a77-142">**Malware**</span><span class="sxs-lookup"><span data-stu-id="a5a77-142">**Malware**</span></span>

5. <span data-ttu-id="a5a77-143">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="a5a77-143">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a5a77-144">![Voorbeeld van nieuwe URL-inzending](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-144">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="a5a77-145">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="a5a77-145">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="a5a77-146">Selecteer url in de vervolgkeuzelijst **in** het vak Selecteer het inzendingstype. </span><span class="sxs-lookup"><span data-stu-id="a5a77-146">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="a5a77-147">Voer in het vak **URL** dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="a5a77-147">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="a5a77-148">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a5a77-148">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a5a77-149">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="a5a77-149">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a5a77-150">**Moet zijn geblokkeerd:** Selecteer **Phish** of Malware in de sectie Deze **URL** moet zijn gecategoriseerd als sectie die wordt **weergegeven.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-150">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="a5a77-151">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="a5a77-151">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a5a77-152">![Voorbeeld van nieuwe e-mailinzending](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-152">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="a5a77-153">Een verdachte e-mailbijlage indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5a77-153">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="a5a77-154">Selecteer bestand in de vervolgkeuzelijst in het vak Selecteer het  **inzendingstype.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-154">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="a5a77-155">Klik in **de** sectie Bestand die wordt weergegeven op **Bestanden bladeren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-155">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="a5a77-156">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-156">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="a5a77-157">Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a5a77-157">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a5a77-158">**Had niet moeten worden geblokkeerd (onwaar positief)**</span><span class="sxs-lookup"><span data-stu-id="a5a77-158">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a5a77-159">**Moet zijn geblokkeerd:** In de deze **URL** moet zijn gecategoriseerd als sectie die wordt weergegeven, **Malware** is de enige keuze en wordt automatisch geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a5a77-159">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="a5a77-160">Wanneer u klaar bent, klikt u op de **knop** Verzenden.</span><span class="sxs-lookup"><span data-stu-id="a5a77-160">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a5a77-161">![Voorbeeld van nieuwe bijlageinzending](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-161">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="a5a77-162">Beheerdersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5a77-162">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="a5a77-163">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-163">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a5a77-164">Controleer op **de pagina Inzendingen** of het tabblad **Ingediend voor analyse** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a5a77-164">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="a5a77-165">U kunt de items sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="a5a77-165">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="a5a77-166">Klik **op Kolommen aanpassen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a5a77-166">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a5a77-167">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a5a77-167">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="a5a77-168">**Inzendingsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-168">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-169">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-169">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-170">**Verzonden datum**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-170">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-171">**Inzendingstype**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-171">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-172">**Reden voor het indienen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-172">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-173">**Status opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-173">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-174">**Resultaat opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-174">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-175">**Filter-uitspraak**</span><span class="sxs-lookup"><span data-stu-id="a5a77-175">**Filter verdict**</span></span>
     - <span data-ttu-id="a5a77-176">**Reden voor bezorging/blokkering**</span><span class="sxs-lookup"><span data-stu-id="a5a77-176">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="a5a77-177">**Inzending-id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-177">**Submission ID**</span></span>
     - <span data-ttu-id="a5a77-178">**Netwerkbericht-id/object-id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-178">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="a5a77-179">**Richting**</span><span class="sxs-lookup"><span data-stu-id="a5a77-179">**Direction**</span></span>
     - <span data-ttu-id="a5a77-180">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="a5a77-180">**Sender IP**</span></span>
     - <span data-ttu-id="a5a77-181">**Bulk compliant level (BCL)**</span><span class="sxs-lookup"><span data-stu-id="a5a77-181">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="a5a77-182">**Destination**</span><span class="sxs-lookup"><span data-stu-id="a5a77-182">**Destination**</span></span>
     - <span data-ttu-id="a5a77-183">**Beleidsactie**</span><span class="sxs-lookup"><span data-stu-id="a5a77-183">**Policy action**</span></span>
     - <span data-ttu-id="a5a77-184">**Ingediend door**</span><span class="sxs-lookup"><span data-stu-id="a5a77-184">**Submitted by**</span></span>

     <span data-ttu-id="a5a77-185">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-185">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="a5a77-186">Als u de items wilt filteren, klikt u op **Filteren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-186">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="a5a77-187">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="a5a77-187">The available filters are:</span></span>
     - <span data-ttu-id="a5a77-188">**Verzonden datum**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="a5a77-188">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="a5a77-189">**Inzendingstype:** **E-mail,** **URL** of **Bestand.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-189">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="a5a77-190">**Inzending-id:** een GUID-waarde die aan elke inzending is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a5a77-190">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="a5a77-191">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-191">**Network Message ID**</span></span>
     - <span data-ttu-id="a5a77-192">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="a5a77-192">**Sender**</span></span>

     <span data-ttu-id="a5a77-193">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-193">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a5a77-194">![Nieuwe filteropties voor beheerdersinzendingen](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-194">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="a5a77-195">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="a5a77-195">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="a5a77-196">**Geen**</span><span class="sxs-lookup"><span data-stu-id="a5a77-196">**None**</span></span>
     - <span data-ttu-id="a5a77-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="a5a77-197">**Type**</span></span>
     - <span data-ttu-id="a5a77-198">**Reden**</span><span class="sxs-lookup"><span data-stu-id="a5a77-198">**Reason**</span></span>
     - <span data-ttu-id="a5a77-199">**Status**</span><span class="sxs-lookup"><span data-stu-id="a5a77-199">**Status**</span></span>
     - <span data-ttu-id="a5a77-200">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="a5a77-200">**Rescan result**</span></span>

   - <span data-ttu-id="a5a77-201">Als u de items wilt exporteren, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-201">To export the entries, click **Export**.</span></span> <span data-ttu-id="a5a77-202">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="a5a77-202">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="a5a77-203">Details van de inzending van beheerders opnieuw scannen</span><span class="sxs-lookup"><span data-stu-id="a5a77-203">Admin submission rescan details</span></span>

<span data-ttu-id="a5a77-204">Berichten die worden verzonden in beheerdersinzendingen, worden beoordeeld en de resultaten worden weergegeven in de flyout details van de inzendingen:</span><span class="sxs-lookup"><span data-stu-id="a5a77-204">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="a5a77-205">Of er tijdens de levering een fout zat in de e-mailverificatie van de afzender.</span><span class="sxs-lookup"><span data-stu-id="a5a77-205">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="a5a77-206">Informatie over eventuele beleidstreffers die het oordeel over een bericht kunnen hebben beïnvloed of overschreven.</span><span class="sxs-lookup"><span data-stu-id="a5a77-206">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="a5a77-207">Huidige deactiveringsresultaten om te zien of de URL's of bestanden in het bericht schadelijk waren of niet.</span><span class="sxs-lookup"><span data-stu-id="a5a77-207">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="a5a77-208">Feedback van cijferaars.</span><span class="sxs-lookup"><span data-stu-id="a5a77-208">Feedback from graders.</span></span>

<span data-ttu-id="a5a77-209">Als een overschrijving is gevonden, zou het opnieuw scannen in enkele minuten moeten zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="a5a77-209">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="a5a77-210">Als er geen probleem was bij e-mailverificatie of bezorging werd niet beïnvloed door een overschrijven, kan de feedback van cijferaars maximaal een dag duren.</span><span class="sxs-lookup"><span data-stu-id="a5a77-210">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="a5a77-211">Gebruikersinzendingen weergeven bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5a77-211">View user submissions to Microsoft</span></span>

<span data-ttu-id="a5a77-212">Als u de invoegvoeging Rapportbericht , de [invoeging](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)melden of personen de [ingebouwde](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapportage in webversie van Outlook hebt  geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Bericht van gebruiker gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="a5a77-212">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="a5a77-213">Ga in Microsoft 365 Defender portal naar **E-mail &** \> **samenwerkingsinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-213">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a5a77-214">Selecteer op **de pagina Inzendingen** het tabblad **Gerapporteerde berichten van gebruiker.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-214">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="a5a77-215">U kunt de items sorteren door op een beschikbare kolomkop te klikken.</span><span class="sxs-lookup"><span data-stu-id="a5a77-215">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="a5a77-216">Klik **op Kolommen aanpassen** om maximaal zeven kolommen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a5a77-216">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a5a77-217">Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a5a77-217">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="a5a77-218">**Onderwerp e-mail**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-218">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-219">**Gerapporteerd door**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-219">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-220">**Datum gerapporteerd**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-220">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-221">**Afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-221">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-222">**Gerapporteerde reden**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-222">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-223">**Resultaat opnieuw scannen**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a5a77-223">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="a5a77-224">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-224">**Message reported ID**</span></span>
     - <span data-ttu-id="a5a77-225">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-225">**Network Message ID**</span></span>
     - <span data-ttu-id="a5a77-226">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="a5a77-226">**Sender IP**</span></span>
     - <span data-ttu-id="a5a77-227">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="a5a77-227">**Phish simulation**</span></span>

     <span data-ttu-id="a5a77-228">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-228">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="a5a77-229">Als u de items wilt filteren, klikt u op **Filteren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-229">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="a5a77-230">De beschikbare filters zijn:</span><span class="sxs-lookup"><span data-stu-id="a5a77-230">The available filters are:</span></span>
     - <span data-ttu-id="a5a77-231">**Datum gerapporteerd**: **Begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="a5a77-231">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="a5a77-232">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="a5a77-232">**Reported by**</span></span>
     - <span data-ttu-id="a5a77-233">**E-mail onderwerp**</span><span class="sxs-lookup"><span data-stu-id="a5a77-233">**Email subject**</span></span>
     - <span data-ttu-id="a5a77-234">**Bericht gerapporteerde id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-234">**Message reported ID**</span></span>
     - <span data-ttu-id="a5a77-235">**Netwerkbericht-id**</span><span class="sxs-lookup"><span data-stu-id="a5a77-235">**Network Message ID**</span></span>
     - <span data-ttu-id="a5a77-236">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="a5a77-236">**Sender**</span></span>
     - <span data-ttu-id="a5a77-237">**Gerapporteerde reden:** **Geen ongewenste** e-mail, **Phish** of **Spam.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-237">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="a5a77-238">**Phish-simulatie:** **Ja** of **Nee**</span><span class="sxs-lookup"><span data-stu-id="a5a77-238">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="a5a77-239">Wanneer u klaar bent, klikt u op **Toepassen.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-239">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a5a77-240">![Nieuwe filteropties voor gebruikersinzendingen](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-240">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="a5a77-241">Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="a5a77-241">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="a5a77-242">**Geen**</span><span class="sxs-lookup"><span data-stu-id="a5a77-242">**None**</span></span>
     - <span data-ttu-id="a5a77-243">**Reden**</span><span class="sxs-lookup"><span data-stu-id="a5a77-243">**Reason**</span></span>
     - <span data-ttu-id="a5a77-244">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="a5a77-244">**Sender**</span></span>
     - <span data-ttu-id="a5a77-245">**Gerapporteerd door**</span><span class="sxs-lookup"><span data-stu-id="a5a77-245">**Reported by**</span></span>
     - <span data-ttu-id="a5a77-246">**Resultaat opnieuw scannen**</span><span class="sxs-lookup"><span data-stu-id="a5a77-246">**Rescan result**</span></span>
     - <span data-ttu-id="a5a77-247">**Phish-simulatie**</span><span class="sxs-lookup"><span data-stu-id="a5a77-247">**Phish simulation**</span></span>

   - <span data-ttu-id="a5a77-248">Als u de items wilt exporteren, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="a5a77-248">To export the entries, click **Export**.</span></span> <span data-ttu-id="a5a77-249">Sla in het dialoogvenster dat wordt weergegeven het .csv op.</span><span class="sxs-lookup"><span data-stu-id="a5a77-249">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="a5a77-250">Als organisaties zijn geconfigureerd om alleen gerapporteerde berichten van gebruikers naar het aangepaste postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in **door** de gebruiker gerapporteerde berichten altijd leeg.</span><span class="sxs-lookup"><span data-stu-id="a5a77-250">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="a5a77-251">Gebruikersinzendingen ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a5a77-251">Undo user submissions</span></span>

<span data-ttu-id="a5a77-252">Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="a5a77-252">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="a5a77-253">Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="a5a77-253">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="a5a77-254">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="a5a77-254">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="a5a77-255">Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="a5a77-255">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="a5a77-256">Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.</span><span class="sxs-lookup"><span data-stu-id="a5a77-256">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="a5a77-257">Selecteer op **het tabblad Gerapporteerde** berichten van gebruiker een bericht in de lijst, klik op Verzenden bij **Microsoft** voor analyse en selecteer vervolgens een van de volgende waarden in de vervolgkeuzelijst:</span><span class="sxs-lookup"><span data-stu-id="a5a77-257">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="a5a77-258">**Rapport opschoon**</span><span class="sxs-lookup"><span data-stu-id="a5a77-258">**Report clean**</span></span>
- <span data-ttu-id="a5a77-259">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="a5a77-259">**Report phishing**</span></span>
- <span data-ttu-id="a5a77-260">**Malware rapporteren**</span><span class="sxs-lookup"><span data-stu-id="a5a77-260">**Report malware**</span></span>
- <span data-ttu-id="a5a77-261">**Spam rapporteren**</span><span class="sxs-lookup"><span data-stu-id="a5a77-261">**Report spam**</span></span>
- <span data-ttu-id="a5a77-262">**Onderzoek starten**</span><span class="sxs-lookup"><span data-stu-id="a5a77-262">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a5a77-263">![Nieuwe opties op de knop Actie](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="a5a77-263">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
