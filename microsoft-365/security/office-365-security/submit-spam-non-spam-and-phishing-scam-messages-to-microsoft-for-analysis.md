---
title: Berichten handmatig indienen bij Microsoft voor analyse
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
description: Beheerders en eindgebruikers kunnen leren hoe ze e-mailberichten (goede e-mail die als slechte of slechte e-mail is toegestaan) naar Microsoft kunnen verzenden voor analyse.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3a02c710472a996245a38d996ff4485efd1748
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624023"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="3a1e7-103">Berichten handmatig indienen bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="3a1e7-103">Manually submit messages to Microsoft for analysis</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a1e7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3a1e7-104">**Applies to**</span></span>
- [<span data-ttu-id="3a1e7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3a1e7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3a1e7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3a1e7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3a1e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a1e7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="3a1e7-108">Als u een beheerder bent in een organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-108">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3a1e7-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="3a1e7-110">Het kan frustrerend zijn als gebruikers in uw organisatie ongewenste e-mailberichten (spam) of phishingberichten ontvangen in hun Postvak IN of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-110">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="3a1e7-111">We passen onze spamfilters voortdurend aan om nauwkeuriger te zijn.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-111">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="3a1e7-112">U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten bij Microsoft in te dienen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-112">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="3a1e7-113">Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-113">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="3a1e7-114">Onwaar negatieven indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a1e7-114">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="3a1e7-115">In plaats van de volgende procedures te gebruiken om onwaar negatieven te rapporteren, kunnen gebruikers in Outlook en Outlook op het web (voorheen bekend als Outlook Web App) de invoegprocedure Rapportbericht of de invoegprocedure Phishing melden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-115">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="3a1e7-116">Zie De invoeging Rapportbericht [inschakelen](enable-the-report-message-add-in.md) en De invoeging Phishing melden inschakelen voor meer informatie over het installeren en gebruiken van [deze hulpprogramma's.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="3a1e7-116">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="3a1e7-117">Als u een bericht ontvangt dat spamfilters heeft ontvangen die als spam of phishing hadden moeten worden geïdentificeerd, kunt u het bericht indien nodig indienen bij de teams Microsoft Spam Analysis en Microsoft Phishing Analysis.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-117">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="3a1e7-118">De analisten bekijken het bericht en voegen het toe aan de filters voor de hele service als het voldoet aan de classificatiecriteria.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-118">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="3a1e7-119">Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:</span><span class="sxs-lookup"><span data-stu-id="3a1e7-119">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="3a1e7-120">**Ongewenste e-mail**: `junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="3a1e7-120">**Junk**: `junk@office365.microsoft.com`</span></span>
   - <span data-ttu-id="3a1e7-121">**Phishing**: `phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="3a1e7-121">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="3a1e7-122">Sleep en drop het ongewenste e-mailbericht of phishingbericht naar het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-122">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="3a1e7-123">Hiermee wordt het ongewenste e-mailbericht of phishingbericht op opslaan als bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-123">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="3a1e7-124">Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="3a1e7-124">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="3a1e7-125">U kunt meerdere berichten in het nieuwe bericht bij elkaar brengen.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-125">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="3a1e7-126">Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-126">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="3a1e7-127">Laat de body van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-127">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="3a1e7-128">Gebruik de indeling .msg (standaardindeling Outlook)of .eml (standaardinstelling Outlook webnotatie) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-128">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="3a1e7-129">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="3a1e7-129">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="3a1e7-130">Beheerders kunnen op verschillende manieren specifieke berichten blokkeren die verkeerd worden geïdentificeerd als spam.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-130">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="3a1e7-131">Zie Geblokkeerde afzenderlijsten maken in EOP voor [meer informatie.](create-block-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3a1e7-131">For details, see [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="3a1e7-132">Fout-positieven indienen bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a1e7-132">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="3a1e7-133">In plaats van de volgende procedures te gebruiken om fout-positieven te rapporteren, kunnen gebruikers in Outlook en Outlook op het web (voorheen bekend als Outlook Web App) de invoegvoegprocedure Rapportbericht of de invoegvoegprocedure Phishing melden gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-133">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="3a1e7-134">Zie De invoeging Rapportbericht [inschakelen](enable-the-report-message-add-in.md) en De invoeging Phishing melden inschakelen voor meer informatie over het installeren en gebruiken van [deze hulpprogramma's.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="3a1e7-134">For information about how to install and use these tools, see [Enable the Report Message add-in](enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="3a1e7-135">Als een bericht onjuist is geïdentificeerd als spam, kunt u het bericht indienen bij het Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-135">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="3a1e7-136">De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) de filters voor de hele service kunnen worden aangepast om het bericht door te sturen.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-136">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="3a1e7-137">Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-137">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient.</span></span>

2. <span data-ttu-id="3a1e7-138">Sleep en zet het verkeerd geïdentificeerde bericht in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-138">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="3a1e7-139">Hiermee wordt het verkeerd geïdentificeerde bericht op opslaan als bijlage in het nieuwe bericht.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-139">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="3a1e7-140">Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).</span><span class="sxs-lookup"><span data-stu-id="3a1e7-140">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="3a1e7-141">U kunt meerdere berichten in het nieuwe bericht bij elkaar brengen.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-141">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="3a1e7-142">Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-142">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span>
   > - <span data-ttu-id="3a1e7-143">Laat de body van het nieuwe bericht leeg.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-143">Leave the body of the new message empty.</span></span>
   > - <span data-ttu-id="3a1e7-144">Gebruik de indeling .msg (standaardindeling Outlook)of .eml (standaardinstelling Outlook webnotatie) voor de bijgevoegde berichten.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-144">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>

3. <span data-ttu-id="3a1e7-145">Wanneer u klaar bent, klikt u op **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="3a1e7-145">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="3a1e7-146">Beheerders kunnen op verschillende manieren toestaan dat specifieke berichten spamfilters overslaan.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-146">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="3a1e7-147">Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="3a1e7-147">For details, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a><span data-ttu-id="3a1e7-148">Waar worden de gegevens uit inzendingen naar Microsoft opgeslagen?</span><span class="sxs-lookup"><span data-stu-id="3a1e7-148">Where is the data from submissions to Microsoft stored?</span></span>

<span data-ttu-id="3a1e7-149">De gegevens bevinden zich in de Office 365 compliancegrens in Noord-Amerikaanse datacenters.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-149">The data resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="3a1e7-150">De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-150">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="3a1e7-151">Een e-mailstroomregel maken om kopieën te ontvangen van berichten die worden gerapporteerd aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a1e7-151">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="3a1e7-152">Zie Regels voor [e-mailstroom gebruiken voor](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)instructies om te zien wat gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a1e7-152">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
