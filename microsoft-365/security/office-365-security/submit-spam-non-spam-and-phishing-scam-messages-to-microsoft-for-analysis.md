---
title: Berichten handmatig verzenden naar Microsoft voor analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'U en uw gebruikers kunnen valse negatieve en fout-positieve spamberichten naar Microsoft sturen voor analyse. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7fc26e1cba976e68b8dcfee5ec8b4fe366b8c47
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035234"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="8279d-103">Berichten handmatig verzenden naar Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="8279d-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="8279d-104">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8279d-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="8279d-105">Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="8279d-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="8279d-106">Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten ontvangen in hun Postvak IN, of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="8279d-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="8279d-107">We verfijnen onze spamfilters voortdurend om nauwkeuriger te zijn.</span><span class="sxs-lookup"><span data-stu-id="8279d-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="8279d-108">U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), valse negatieven (slechte e-mail toegestaan) en phishing-berichten bij Microsoft in te dienen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="8279d-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="8279d-109">Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="8279d-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="8279d-110">Valse negatieven verzenden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="8279d-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="8279d-111">In plaats van de volgende procedures te gebruiken om valse negatieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook (voorheen Outlook Web App) de invoegtoepassing Berichtrapport voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8279d-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="8279d-112">Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.</span><span class="sxs-lookup"><span data-stu-id="8279d-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="8279d-113">Als u een bericht ontvangt dat door spamfiltering is verzonden en dat als spam of phishing had moeten worden geïdentificeerd, u het bericht naar gelang van het geval indienen bij de microsoft spamanalyse- en Microsoft Phishing-analyseteams.</span><span class="sxs-lookup"><span data-stu-id="8279d-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="8279d-114">De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="8279d-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="8279d-115">Maak een nieuw, leeg e-mailbericht met een van de volgende ontvangers:</span><span class="sxs-lookup"><span data-stu-id="8279d-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="8279d-116">**Junk**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="8279d-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="8279d-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="8279d-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="8279d-118">Sleep en drop de ongewenste of phishing-bericht in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="8279d-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="8279d-119">Dit zal de junk of phishing-bericht op te slaan als een bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="8279d-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="8279d-120">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).</span><span class="sxs-lookup"><span data-stu-id="8279d-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="8279d-121">U meerdere berichten toevoegen in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="8279d-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="8279d-122">Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="8279d-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="8279d-123">Laat het lichaam van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="8279d-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="8279d-124">Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="8279d-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="8279d-125">Klik op **Verzenden**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8279d-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="8279d-126">Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die verkeerd worden geïdentificeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="8279d-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="8279d-127">Zie Lijsten [met geblokkeerde afzenders maken in Office 365](create-block-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8279d-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="8279d-128">Valse positieven verzenden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="8279d-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="8279d-129">In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8279d-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="8279d-130">Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.</span><span class="sxs-lookup"><span data-stu-id="8279d-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="8279d-131">Als een bericht ten onrechte is geïdentificeerd als spam, u het bericht indienen bij het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="8279d-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="8279d-132">De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) kunnen de servicebrede filters worden aangepast om het bericht door te laten gaan.</span><span class="sxs-lookup"><span data-stu-id="8279d-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="8279d-133">Maak een nieuw, leeg `not_junk@office365.microsoft.com` e-mailbericht met als ontvanger:</span><span class="sxs-lookup"><span data-stu-id="8279d-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="8279d-134">Sleep en laat het verkeerd geïdentificeerde bericht in het nieuwe bericht vallen.</span><span class="sxs-lookup"><span data-stu-id="8279d-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="8279d-135">Hiermee wordt het verkeerd geïdentificeerde bericht opgeslagen als bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="8279d-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="8279d-136">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).</span><span class="sxs-lookup"><span data-stu-id="8279d-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="8279d-137">U meerdere berichten toevoegen in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="8279d-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="8279d-138">Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="8279d-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="8279d-139">Laat het lichaam van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="8279d-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="8279d-140">Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="8279d-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="8279d-141">Klik op **Verzenden**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="8279d-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="8279d-142">Beheerders hebben verschillende manieren om specifieke berichten toe te staan spamfilters over te slaan.</span><span class="sxs-lookup"><span data-stu-id="8279d-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="8279d-143">Zie Lijsten [met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8279d-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="8279d-144">Een e-mailstroomregel maken om kopieën te ontvangen van berichten die aan Microsoft worden gerapporteerd</span><span class="sxs-lookup"><span data-stu-id="8279d-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="8279d-145">Zie Regels [voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8279d-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
