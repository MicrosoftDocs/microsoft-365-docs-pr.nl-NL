---
title: Berichten handmatig bij Microsoft indienen voor analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Beheerders en eindgebruikers kunnen zien hoe u e-mailberichten (goede e-mailberichten die zijn gemarkeerd als beschadigd of niet toegestaan) in Microsoft voor analyse.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68a0921f85e5b916cd53ebe84e4ea7d35e39967e
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877703"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="7e0fe-103">Berichten handmatig bij Microsoft indienen voor analyse</span><span class="sxs-lookup"><span data-stu-id="7e0fe-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="7e0fe-104">Als u een beheerder bent van een organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7e0fe-105">Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7e0fe-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="7e0fe-106">Dit kan vervelend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten in hun postvak in ontvangen, of als ze geen legitiem e-mailbericht ontvangen, omdat dit als ongewenste e-mail is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="7e0fe-107">Onze spamfilters worden continu nauwkeuriger afgestemd.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="7e0fe-108">U en uw gebruikers kunnen dit proces helpen met het indienen van foutberichten (goede e-mailberichten die als beschadigd zijn gemarkeerd), onjuiste negatieven (onjuiste e-mail toegestaan) en phishingberichten aan Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="7e0fe-109">Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="7e0fe-110">Onjuiste negatieven bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="7e0fe-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="7e0fe-111">In plaats van de volgende procedures te gebruiken voor het melden van onjuiste negatieven, gebruikers in Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen de invoegtoepassing bericht rapporteren voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="7e0fe-112">Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="7e0fe-113">Als u een bericht ontvangt dat via spam filtert dat als spam of phishing werd herkend, kunt u het bericht naar de Microsoft spam analyse en Microsoft phishing-teams verzenden.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="7e0fe-114">De analisten beoordelen het bericht en voeg dit toe aan de service filters, als dit voldoet aan de classificatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="7e0fe-115">Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:</span><span class="sxs-lookup"><span data-stu-id="7e0fe-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="7e0fe-116">**Ongewenste e-mail** : `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="7e0fe-116">**Junk** : `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="7e0fe-117">**Phishing** : `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="7e0fe-117">**Phishing** : `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="7e0fe-118">Sleep de ongewenste e-mail of het bericht naar het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="7e0fe-119">Hierdoor wordt het ongewenste e-mailbericht of het bericht opgeslagen als een bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="7e0fe-120">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="7e0fe-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7e0fe-121">U kunt meerdere berichten toevoegen aan het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="7e0fe-122">Zorg ervoor dat alle berichten hetzelfde type hebben: malafide berichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-122">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="7e0fe-123">Laat de tekst van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-123">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="7e0fe-124">Gebruik. msg (standaardindeling van Outlook) of. eml (standaardindeling van de webversie van Outlook) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="7e0fe-125">Wanneer u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="7e0fe-126">Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die niet goed worden geïdentificeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="7e0fe-127">Zie [lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-127">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="7e0fe-128">Vervalste naar Microsoft verzenden</span><span class="sxs-lookup"><span data-stu-id="7e0fe-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="7e0fe-129">In plaats van de volgende procedures voor het melden van foutberichten, gebruikers in Outlook en de webversie van Outlook kunnen de invoegtoepassing bericht rapporteren voor Microsoft Outlook gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="7e0fe-130">Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="7e0fe-131">Als een bericht onjuist is aangemerkt als ongewenste e-mail, kunt u het bericht indienen bij het team van Microsoft spam analyses.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="7e0fe-132">Op de analisten wordt het bericht geëvalueerd en (afhankelijk van de resultaten van de analyse) kunnen de service-Wide filters worden aangepast om het bericht toe te staan.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="7e0fe-133">Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` de ontvanger:</span><span class="sxs-lookup"><span data-stu-id="7e0fe-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="7e0fe-134">Sleep en zet het foutbericht in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="7e0fe-135">Hierdoor wordt het foutbericht in het nieuwe bericht opgeslagen als een bijlage.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="7e0fe-136">Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="7e0fe-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7e0fe-137">U kunt meerdere berichten toevoegen aan het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="7e0fe-138">Zorg ervoor dat alle berichten hetzelfde type hebben: malafide berichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   >
   > - <span data-ttu-id="7e0fe-139">Laat de tekst van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-139">Leave the body of the new message empty.</span></span>
   >
   > - <span data-ttu-id="7e0fe-140">Gebruik. msg (standaardindeling van Outlook) of. eml (standaardindeling van de webversie van Outlook) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="7e0fe-141">Wanneer u klaar bent, klikt u op **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="7e0fe-142">Beheerders hebben verschillende manieren om te voorkomen dat specifieke berichten worden gefilterd door het filteren van spam.</span><span class="sxs-lookup"><span data-stu-id="7e0fe-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="7e0fe-143">Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="7e0fe-143">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="7e0fe-144">Een e-mail stroom regel maken om kopieën te ontvangen van berichten die bij Microsoft worden gerapporteerd</span><span class="sxs-lookup"><span data-stu-id="7e0fe-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="7e0fe-145">Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7e0fe-145">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
