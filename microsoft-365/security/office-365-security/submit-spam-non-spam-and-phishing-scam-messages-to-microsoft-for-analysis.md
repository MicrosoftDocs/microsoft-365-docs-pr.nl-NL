---
title: Berichten handmatig naar Microsoft verzenden voor analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Beheerders en eindgebruikers kunnen voor analyse leren hoe ze e-mailberichten (goede e-mailberichten die als slecht of slecht zijn gemarkeerd) kunnen verzenden naar Microsoft.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290367"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="debb7-103">Berichten handmatig naar Microsoft verzenden voor analyse</span><span class="sxs-lookup"><span data-stu-id="debb7-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="debb7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="debb7-104">**Applies to**</span></span>
- [<span data-ttu-id="debb7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="debb7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="debb7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="debb7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="debb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="debb7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="debb7-108">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="debb7-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="debb7-109">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="debb7-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="debb7-110">Dit kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste e-mail (spam) of phishingberichten in hun Postvak IN ontvangen of als ze geen legitiem e-mailbericht ontvangen omdat het als ongewenste e-mail is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="debb7-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="debb7-111">We zijn voortdurend bezig onze spamfilters nauwkeuriger aan te passen.</span><span class="sxs-lookup"><span data-stu-id="debb7-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="debb7-112">U en uw gebruikers kunnen dit proces helpen door fout-positieven (goede e-mail gemarkeerd als slecht), fout-negatieven (slechte e-mail toegestaan) en phishingberichten naar Microsoft te verzenden voor analyse.</span><span class="sxs-lookup"><span data-stu-id="debb7-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="debb7-113">Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="debb7-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="debb7-114">Fout-negatieven indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="debb7-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="debb7-115">In plaats van de volgende procedures te gebruiken voor het rapporteren van fout-negatieven, kunnen gebruikers in outlook en de webversie van Outlook (voorheen Outlook Web App) de invoegversie Bericht rapporteren of Phishing melden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="debb7-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="debb7-116">Voor meer informatie over het installeren en gebruiken van deze hulpprogramma's, zie De invoegapp Bericht rapporteren inschakelen en De [phishing-invoegapp](enable-the-report-message-add-in.md) voor het melden [inschakelen.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="debb7-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="debb7-117">Als u een bericht ontvangt dat is gefilterd door spamfilters die moeten zijn aangemerkt als spam of phishing, kunt u het bericht verzenden naar de teams Microsoft Spam-analyse en Microsoft Phishing-analyse.</span><span class="sxs-lookup"><span data-stu-id="debb7-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="debb7-118">De analisten zullen het bericht beoordelen en toevoegen aan de filters voor de hele service als het aan de classificatiecriteria voldoet.</span><span class="sxs-lookup"><span data-stu-id="debb7-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="debb7-119">Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:</span><span class="sxs-lookup"><span data-stu-id="debb7-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="debb7-120">**Ongewenste e-mail:**`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="debb7-120">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="debb7-121">**Phishing:**`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="debb7-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="debb7-122">Sleep de ongewenste e-mail of het phishingbericht naar het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="debb7-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="debb7-123">Het ongewenste e-mail- of phishingbericht wordt dan als bijlage in het nieuwe bericht op slaan.</span><span class="sxs-lookup"><span data-stu-id="debb7-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="debb7-124">Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="debb7-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="debb7-125">U kunt meerdere berichten aan het nieuwe bericht koppelen.</span><span class="sxs-lookup"><span data-stu-id="debb7-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="debb7-126">Zorg ervoor dat alle berichten van hetzelfde type zijn: phishing-berichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="debb7-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="debb7-127">Laat de tekst van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="debb7-127">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="debb7-128">Gebruik de indeling .msg (standaard Outlook-indeling) of EML-indeling (standaardindeling in de webversie van Outlook) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="debb7-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="debb7-129">Klik op Verzenden wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="debb7-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="debb7-130">Beheerders kunnen op verschillende manieren specifieke berichten blokkeren die verkeerd worden aangemerkt als spam.</span><span class="sxs-lookup"><span data-stu-id="debb7-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="debb7-131">Zie Lijsten met geblokkeerde afzenders maken [in EOP voor meer informatie.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="debb7-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="debb7-132">Fout-positieven indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="debb7-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="debb7-133">In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in outlook en de webversie van Outlook (voorheen Outlook Web App) de invoegversie Bericht rapporteren of Phishing melden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="debb7-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="debb7-134">Voor meer informatie over het installeren en gebruiken van deze hulpprogramma's, zie De invoegapp Bericht rapporteren inschakelen en De [phishing-invoegapp](enable-the-report-message-add-in.md) voor het melden [inschakelen.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="debb7-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>


<span data-ttu-id="debb7-135">Als een bericht ten onrechte als spam is aangemerkt, kunt u het verzenden naar het Microsoft-team voor spamanalyse.</span><span class="sxs-lookup"><span data-stu-id="debb7-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="debb7-136">De analisten zullen het bericht evalueren en (afhankelijk van de resultaten van de analyse) de filters voor de hele service kunnen worden aangepast om het bericht door te sturen.</span><span class="sxs-lookup"><span data-stu-id="debb7-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="debb7-137">Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als geadresseerde:</span><span class="sxs-lookup"><span data-stu-id="debb7-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="debb7-138">Sleep het verkeerd geïdentificeerde bericht naar het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="debb7-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="debb7-139">Hierdoor wordt het verkeerd geïdentificeerde bericht als bijlage in het nieuwe bericht op slaan.</span><span class="sxs-lookup"><span data-stu-id="debb7-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="debb7-140">Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="debb7-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="debb7-141">U kunt meerdere berichten aan het nieuwe bericht koppelen.</span><span class="sxs-lookup"><span data-stu-id="debb7-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="debb7-142">Zorg ervoor dat alle berichten van hetzelfde type zijn: phishing-berichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="debb7-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="debb7-143">Laat de tekst van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="debb7-143">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="debb7-144">Gebruik de indeling .msg (standaard Outlook-indeling) of EML-indeling (standaardindeling in de webversie van Outlook) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="debb7-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="debb7-145">Klik op Verzenden wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="debb7-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="debb7-146">Beheerders hebben verschillende manieren om toe te staan dat specifieke berichten spamfilters overslaan.</span><span class="sxs-lookup"><span data-stu-id="debb7-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="debb7-147">Zie Lijsten met veilige [afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="debb7-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="debb7-148">Waar worden de gegevens van inzendingen bij Microsoft opgeslagen?</span><span class="sxs-lookup"><span data-stu-id="debb7-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="debb7-149">De gegevens bevinden zich in de nalevingsgrens van Office 365 in het Noord-Amerikaanse datacenter.</span><span class="sxs-lookup"><span data-stu-id="debb7-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="debb7-150">De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te helpen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="debb7-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="debb7-151">Een regel voor de e-mailstroom maken om kopieën te ontvangen van berichten die worden gerapporteerd bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="debb7-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="debb7-152">Zie Regels voor [e-mailstroom gebruiken om te zien wat uw gebruikers melden bij Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="debb7-152">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
