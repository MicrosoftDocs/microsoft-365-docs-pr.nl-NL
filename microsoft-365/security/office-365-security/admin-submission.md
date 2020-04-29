---
title: Admin inzendingen, inzendingen, spam probleem, vals negatief, phish indienen, e-mail indienen voor het scannen, verdachte e-mail in Office 365, een e-mail scannen, hebben Microsoft scannen op phish, hebben Microsoft scannen op spam, e-mail indienen, e-mail indienen, dodgy e-mail, slechte actor e-mail, verdachte, niet-vertrouwde e-mail, verslag phish e-mails aan Microsoft, verslag uitschrijven van kwaadaardige e-mail aan Microsoft, verslag scam e-mail naar Microsoft, verslag scam e-mail aan Microsoft, verslag kwaadaardige e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail naar Microsoft, verslag scam e-mail aan Microsoft, verslag kwaadaardige e-mail aan Microsoft, verslag scam e-mail naar Microsoft, verslag scam e-mail naar Microsoft, verslag scam scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag kwaadaardige e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail aan Microsoft, verslag scam e-mail naar Microsoft, verslag scam e-mail naar Microsoft, verslag scam e-mail aan Microsoft, verslag kwaadaardige e-mail aan , malware in e-mail rapporteren aan Microsoft, spam e-mail in inbox, virus in e-mail
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
description: Meer informatie over het verzenden van verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden van uw bedrijf bij Microsoft voor het scannen.
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921505"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="642d2-103">Beheerbeheer gebruiken om vermoedelijke spam, phish, URL's en bestanden bij Microsoft in te dienen</span><span class="sxs-lookup"><span data-stu-id="642d2-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="642d2-104">Als u een beheerder bent in een Microsoft 365-organisatie met postvakken in Exchange Online, u de inzendingenportal in het Beveiligingscentrum & Compliance Center gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen om te scannen.</span><span class="sxs-lookup"><span data-stu-id="642d2-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="642d2-105">Wanneer u een e-mail indient, ontvangt u informatie over het beleid dat de binnenkomende e-mail mogelijk in uw tenant heeft toegestaan, evenals het onderzoeken van URL's en bijlagen in de e-mail.</span><span class="sxs-lookup"><span data-stu-id="642d2-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="642d2-106">Beleidsregels waarmee een e-mail mogelijk is toegestaan, bevatten de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals de regels voor de e-mailstroom van Exchange (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="642d2-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="642d2-107">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere manieren om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="642d2-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="642d2-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="642d2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="642d2-109">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="642d2-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="642d2-110">Als u rechtstreeks naar de <https://protection.office.com/reportsubmission>pagina **Indiening** wilt gaan, gebruikt u .</span><span class="sxs-lookup"><span data-stu-id="642d2-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="642d2-111">U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="642d2-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="642d2-112">Als u antispambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer,** **Beveiligingsbeheerder**of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="642d2-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="642d2-113">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="642d2-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="642d2-114">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen verzenden naar [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="642d2-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="642d2-115">Verdachte inhoud melden aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="642d2-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="642d2-116">Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="642d2-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="642d2-117">Klik op de pagina **Inzendingen** die wordt weergegeven op de knop **Nieuwe inzending.**</span><span class="sxs-lookup"><span data-stu-id="642d2-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="642d2-118">Gebruik **Nieuwe flyout voor indiening** die wordt weergegeven om het bericht, de URL of de bijlage in te dienen, zoals beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="642d2-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="642d2-119">Een twijfelachtige e-mail verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="642d2-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="642d2-120">Selecteer **E-mail**in de sectie **Objecttype** .</span><span class="sxs-lookup"><span data-stu-id="642d2-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="642d2-121">Gebruik in de sectie **Indieningsvorm** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="642d2-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="642d2-122">**Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-Id** in het bericht.</span><span class="sxs-lookup"><span data-stu-id="642d2-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="642d2-123">**Bestand:** klik op **Bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="642d2-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="642d2-124">Zoek en selecteer in het dialoogvenster dat wordt geopend het bestand .eml of .msg en klik vervolgens op **Openen**.</span><span class="sxs-lookup"><span data-stu-id="642d2-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="642d2-125">Geef **in** de sectie Ontvangers een of meer ontvangers op waartegen u een beleidscontrole wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="642d2-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="642d2-126">De beleidscontrole bepaalt of de e-mail scannen heeft omzeild vanwege het gebruikers- of organisatiebeleid.</span><span class="sxs-lookup"><span data-stu-id="642d2-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="642d2-127">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="642d2-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="642d2-128">**Had niet mogen worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="642d2-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="642d2-129">**Had moeten worden geblokkeerd**: Selecteer **Spam,** **Phishing**of **Malware**.</span><span class="sxs-lookup"><span data-stu-id="642d2-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="642d2-130">Als je het niet zeker weet, gebruik dan je beste oordeel.</span><span class="sxs-lookup"><span data-stu-id="642d2-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="642d2-131">Als het filter is omzeild vanwege het beleid bij indiening, ziet u informatie over dat beleid.</span><span class="sxs-lookup"><span data-stu-id="642d2-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="642d2-132">Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid.</span><span class="sxs-lookup"><span data-stu-id="642d2-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="642d2-133">U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken.</span><span class="sxs-lookup"><span data-stu-id="642d2-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="642d2-134">Dit omvat de resultaten van de beleidscontrole en het rescanvonnis.</span><span class="sxs-lookup"><span data-stu-id="642d2-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="642d2-135">Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstapel van Office 365 ATP, maar dat er een gedeeltelijke recan wordt uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.</span><span class="sxs-lookup"><span data-stu-id="642d2-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="642d2-136">Klik op **Verzenden** als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="642d2-136">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="642d2-138">Een verdachte URL naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="642d2-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="642d2-139">Selecteer **URL**in de sectie **Objecttype** .</span><span class="sxs-lookup"><span data-stu-id="642d2-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="642d2-140">Voer in het vak dat wordt weergegeven <https://www.fabrikam.com/marketing.html>de volledige URL in (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="642d2-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="642d2-141">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="642d2-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="642d2-142">**Had niet mogen worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="642d2-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="642d2-143">**Had moeten worden geblokkeerd**: Selecteer **Phishing** of **Malware**.</span><span class="sxs-lookup"><span data-stu-id="642d2-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="642d2-144">Klik op **Verzenden** als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="642d2-144">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van e-mailindiening](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="642d2-146">Een verdacht bestand indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="642d2-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="642d2-147">Selecteer **bijlage**in de sectie **Objecttype** .</span><span class="sxs-lookup"><span data-stu-id="642d2-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="642d2-148">Klik **op Bestand kiezen**.</span><span class="sxs-lookup"><span data-stu-id="642d2-148">Click **Choose File**.</span></span> <span data-ttu-id="642d2-149">Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en selecteer het bestand en klik vervolgens op **Openen**.</span><span class="sxs-lookup"><span data-stu-id="642d2-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="642d2-150">Selecteer in de sectie **Reden voor indiening** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="642d2-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="642d2-151">**Had niet mogen worden geblokkeerd**</span><span class="sxs-lookup"><span data-stu-id="642d2-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="642d2-152">**Moet zijn geblokkeerd**: **Malware** is de enige keuze, en wordt automatisch geselecteerd..</span><span class="sxs-lookup"><span data-stu-id="642d2-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="642d2-153">Klik op **Verzenden** als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="642d2-153">When you're finished, click the **Submit** button.</span></span>

![Voorbeeld van het indienen van bijlagen](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="642d2-155">Beheerdersinzendingen weergeven</span><span class="sxs-lookup"><span data-stu-id="642d2-155">View admin submissions</span></span>

1. <span data-ttu-id="642d2-156">Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="642d2-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="642d2-157">Controleer op de pagina **Inzendingen** die wordt weergegeven of het tabblad **Inzendingen beheerder** is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="642d2-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="642d2-158">Boven aan de pagina u een begindatum, een einddatum en (standaard) filteren op **indienings-id** door ![een](../../media/scc-quarantine-refresh.png)waarde in het vak in te voeren en op Knop Vernieuwen te klikken.</span><span class="sxs-lookup"><span data-stu-id="642d2-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="642d2-159">U meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="642d2-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="642d2-160">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indiening-id** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="642d2-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="642d2-161">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="642d2-161">**Sender**</span></span>
- <span data-ttu-id="642d2-162">**Onderwerp/URL/bestandsnaam**</span><span class="sxs-lookup"><span data-stu-id="642d2-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="642d2-163">**Afkomstig**</span><span class="sxs-lookup"><span data-stu-id="642d2-163">**Submitted by**</span></span>
- <span data-ttu-id="642d2-164">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-164">**Submission type**</span></span>
- <span data-ttu-id="642d2-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="642d2-165">**Status**</span></span>

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="642d2-167">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**.</span><span class="sxs-lookup"><span data-stu-id="642d2-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="642d2-168">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="642d2-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="642d2-169">Onder de grafiek staan drie tabbladen: **E-mail** (standaard), **URL**en **bijlage**.</span><span class="sxs-lookup"><span data-stu-id="642d2-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="642d2-170">E-mailinzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="642d2-170">View admin email submissions</span></span>

<span data-ttu-id="642d2-171">Klik op het tabblad **E-mail.**</span><span class="sxs-lookup"><span data-stu-id="642d2-171">Click the **Email** tab.</span></span>

<span data-ttu-id="642d2-172">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="642d2-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="642d2-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="642d2-173">**Date**</span></span>
- <span data-ttu-id="642d2-174">**Inzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="642d2-174">**Submission ID**</span></span>
- <span data-ttu-id="642d2-175">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-176">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-177">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="642d2-177">**Sender**</span></span>
- <span data-ttu-id="642d2-178">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-179">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-179">**Submission type**</span></span>
- <span data-ttu-id="642d2-180">**Leveringsreden**</span><span class="sxs-lookup"><span data-stu-id="642d2-180">**Delivery reason**</span></span>
- <span data-ttu-id="642d2-181">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-182">**Besturingstype**</span><span class="sxs-lookup"><span data-stu-id="642d2-182">**Control type**</span></span>
- <span data-ttu-id="642d2-183">**Controlebron**</span><span class="sxs-lookup"><span data-stu-id="642d2-183">**Control source**</span></span>

  <span data-ttu-id="642d2-184"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="642d2-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="642d2-185">URL-inzendingen voor beheerders weergeven</span><span class="sxs-lookup"><span data-stu-id="642d2-185">View admin URL submissions</span></span>

<span data-ttu-id="642d2-186">Klik op het **tabblad URL.**</span><span class="sxs-lookup"><span data-stu-id="642d2-186">Click the **URL** tab.</span></span>

<span data-ttu-id="642d2-187">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="642d2-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="642d2-188">**Datum**</span><span class="sxs-lookup"><span data-stu-id="642d2-188">**Date**</span></span>
- <span data-ttu-id="642d2-189">**Inzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="642d2-189">**Submission ID**</span></span>
- <span data-ttu-id="642d2-190">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-191">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-192">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-192">**Submission type**</span></span>
- <span data-ttu-id="642d2-193">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="642d2-194"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="642d2-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="642d2-195">Inzendingen voor beheerdersbijlagen weergeven</span><span class="sxs-lookup"><span data-stu-id="642d2-195">View admin attachment submissions</span></span>

<span data-ttu-id="642d2-196">Klik op het tabblad **Bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="642d2-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="642d2-197">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="642d2-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="642d2-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="642d2-198">**Date**</span></span>
- <span data-ttu-id="642d2-199">**Inzendings-ID**</span><span class="sxs-lookup"><span data-stu-id="642d2-199">**Submission ID**</span></span>
- <span data-ttu-id="642d2-200">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-201">**Bestandsnaam**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-202">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-202">**Submission type**</span></span>
- <span data-ttu-id="642d2-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="642d2-204"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="642d2-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="642d2-205">Inzendingen van gebruikers bij Microsoft weergeven</span><span class="sxs-lookup"><span data-stu-id="642d2-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="642d2-206">Als u de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)hebt geïmplementeerd of als mensen de [ingebouwde rapportage gebruiken in de webversie van Outlook,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)u zien welke gebruikers rapporteren op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="642d2-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="642d2-207">Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="642d2-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="642d2-208">Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Gebruikersinzendingen.**</span><span class="sxs-lookup"><span data-stu-id="642d2-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="642d2-209">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="642d2-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="642d2-210">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="642d2-210">**Submitted on**</span></span>
- <span data-ttu-id="642d2-211">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-212">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-213">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="642d2-213">**Sender**</span></span>
- <span data-ttu-id="642d2-214">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-215">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-215">**Submission type**</span></span>

<span data-ttu-id="642d2-216"><sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.</span><span class="sxs-lookup"><span data-stu-id="642d2-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="642d2-217">Boven aan de pagina u een begindatum, een einddatum en (standaard) filteren op **afzender** door een ![waarde](../../media/scc-quarantine-refresh.png)in het vak in te voeren en op Knop Vernieuwen te klikken.</span><span class="sxs-lookup"><span data-stu-id="642d2-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="642d2-218">U meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="642d2-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="642d2-219">Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="642d2-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="642d2-220">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="642d2-220">**Sender domain**</span></span>
- <span data-ttu-id="642d2-221">**Onderwerp**</span><span class="sxs-lookup"><span data-stu-id="642d2-221">**Subject**</span></span>
- <span data-ttu-id="642d2-222">**Afkomstig**</span><span class="sxs-lookup"><span data-stu-id="642d2-222">**Submitted by**</span></span>
- <span data-ttu-id="642d2-223">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-223">**Submission type**</span></span>
- <span data-ttu-id="642d2-224">**Ip-afzender**</span><span class="sxs-lookup"><span data-stu-id="642d2-224">**Sender IP**</span></span>

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

<span data-ttu-id="642d2-226">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**.</span><span class="sxs-lookup"><span data-stu-id="642d2-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="642d2-227">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="642d2-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="642d2-228">Inzendingen van gebruikers weergeven in het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="642d2-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="642d2-229">Als u [een aangepast postvak](user-submission.md) hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, u berichten die zijn afgeleverd in het rapportagepostvak bekijken en verzenden.</span><span class="sxs-lookup"><span data-stu-id="642d2-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="642d2-230">Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**</span><span class="sxs-lookup"><span data-stu-id="642d2-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="642d2-231">Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Aangepast postvak.**</span><span class="sxs-lookup"><span data-stu-id="642d2-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="642d2-232">U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="642d2-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="642d2-233">**Ingediend op**</span><span class="sxs-lookup"><span data-stu-id="642d2-233">**Submitted on**</span></span>
- <span data-ttu-id="642d2-234">**Afkomstig**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-235">**Onderwerp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-236">**Afzender**</span><span class="sxs-lookup"><span data-stu-id="642d2-236">**Sender**</span></span>
- <span data-ttu-id="642d2-237">**Ip-afzender**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="642d2-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="642d2-238">**Type inzending**</span><span class="sxs-lookup"><span data-stu-id="642d2-238">**Submission type**</span></span>

<span data-ttu-id="642d2-239">Boven aan de pagina u een begindatum, een einddatum invoeren en u filteren op **Verzenden door** een waarde in het vak in te voeren en op knop Vernieuwen te ![](../../media/scc-quarantine-refresh.png)klikken.</span><span class="sxs-lookup"><span data-stu-id="642d2-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="642d2-240">U meerdere waarden invoeren die zijn gescheiden door komma's.</span><span class="sxs-lookup"><span data-stu-id="642d2-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="642d2-241">Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**.</span><span class="sxs-lookup"><span data-stu-id="642d2-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="642d2-242">Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.</span><span class="sxs-lookup"><span data-stu-id="642d2-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="642d2-243">Berichten verzenden naar Microsoft vanuit het aangepaste postvak</span><span class="sxs-lookup"><span data-stu-id="642d2-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="642d2-244">Als u het aangepaste postvak hebt geconfigureerd om door gebruikers gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, u specifieke berichten voor analyse naar Microsoft zoeken en verzenden.</span><span class="sxs-lookup"><span data-stu-id="642d2-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="642d2-245">Hiermee wordt een gebruiker inplaats gezet in een beheerdersinzending.</span><span class="sxs-lookup"><span data-stu-id="642d2-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="642d2-246">Selecteer op het tabblad **Aangepast postvak** een bericht in de lijst, klik op de knop **Actie** en maak een van de volgende selecties:</span><span class="sxs-lookup"><span data-stu-id="642d2-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="642d2-247">**Rapport schoon**</span><span class="sxs-lookup"><span data-stu-id="642d2-247">**Report clean**</span></span>
- <span data-ttu-id="642d2-248">**Phishing melden**</span><span class="sxs-lookup"><span data-stu-id="642d2-248">**Report phishing**</span></span>
- <span data-ttu-id="642d2-249">**Malware melden**</span><span class="sxs-lookup"><span data-stu-id="642d2-249">**Report malware**</span></span>
- <span data-ttu-id="642d2-250">**Spam melden**</span><span class="sxs-lookup"><span data-stu-id="642d2-250">**Report spam**</span></span>

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
