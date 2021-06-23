---
title: Spam, niet-spam en phishingberichten rapporteren aan Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over de verschillende manieren om goede en slechte berichten en bestanden te rapporteren aan Microsoft voor analyse.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082814"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="da40c-103">Berichten en bestanden rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="da40c-103">Report messages and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="da40c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="da40c-104">**Applies to**</span></span>
- [<span data-ttu-id="da40c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="da40c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="da40c-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="da40c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="da40c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da40c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="da40c-108">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, hebben zowel gebruikers als beheerders verschillende methoden voor het rapporteren van e-mailberichten en bestanden aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da40c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, both users and admins have several different methods for reporting email messages and files to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="da40c-109">Methode</span><span class="sxs-lookup"><span data-stu-id="da40c-109">Method</span></span>|<span data-ttu-id="da40c-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="da40c-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="da40c-111">Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden</span><span class="sxs-lookup"><span data-stu-id="da40c-111">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="da40c-112">De aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online postvakken (niet beschikbaar in zelfstandige EOP).</span><span class="sxs-lookup"><span data-stu-id="da40c-112">The recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="da40c-113">Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="da40c-113">Enable the Report Message or the Report Phishing add-ins</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="da40c-114">Werkt met Outlook en webversie van Outlook (voorheen bekend als Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="da40c-114">Works with Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <p> <span data-ttu-id="da40c-115">Afhankelijk van uw abonnement zijn berichten die gebruikers met de invoegvoegingen hebben gerapporteerd, beschikbaar in de portal Admin [Submissions](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="da40c-115">Depending on your subscription, messages that users reported with the add-ins are available in [the Admin Submissions portal](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions).</span></span> <p> <span data-ttu-id="da40c-116">U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="da40c-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="da40c-117">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="da40c-117">For more information, see [User submissions policies](user-submission.md).</span></span>
|[<span data-ttu-id="da40c-118">Fout-positieven en fout-negatieven rapporteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="da40c-118">Report false positives and false negatives in Outlook</span></span>](report-false-positives-and-false-negatives.md)|<span data-ttu-id="da40c-119">Verzend fout-positieven (goede e-mail die is geblokkeerd of verzonden naar de map Ongewenste e-mail) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) naar Exchange Online Protection (EOP) met de functie Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="da40c-119">Submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP) using the Report Message feature.</span></span>|
|[<span data-ttu-id="da40c-120">Berichten handmatig indienen bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="da40c-120">Manually submit messages to Microsoft for analysis</span></span>](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|<span data-ttu-id="da40c-121">Handmatig bijgevoegde berichten verzenden naar specifieke Microsoft-e-mailadressen voor spam, geen spam en phishing.</span><span class="sxs-lookup"><span data-stu-id="da40c-121">Manually send attached messages to specific Microsoft email addresses for spam, not spam, and phishing.</span></span>|
|[<span data-ttu-id="da40c-122">Regels voor e-mailstromen gebruiken om te zien wat gebruikers melden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="da40c-122">Use mail flow rules to see what users are reporting to Microsoft</span></span>](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|<span data-ttu-id="da40c-123">Meer informatie over het maken van een regel voor e-mailstroom (ook wel transportregel genoemd) die u op de melding stelt wanneer gebruikers berichten rapporteren aan Microsoft voor analyse.</span><span class="sxs-lookup"><span data-stu-id="da40c-123">Learn how to create a mail flow rule (also known as a transport rule) that notifies you when users report messages to Microsoft for analysis.</span></span>|
|[<span data-ttu-id="da40c-124">Malware en niet-malware indienen bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="da40c-124">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="da40c-125">Gebruik de Microsoft-beveiligingsinformatie site om bijlagen en andere bestanden in te dienen.</span><span class="sxs-lookup"><span data-stu-id="da40c-125">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="da40c-126">Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van bezorgd, kunnen gebruikers de berichten rapporteren aan Microsoft vanuit Quarantaine in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="da40c-126">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from Quarantine in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="da40c-127">Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in](find-and-release-quarantined-messages-as-a-user.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da40c-127">For details, see [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da40c-128">Gegevens uit inzendingen naar Microsoft bevinden zich in de Office 365 compliancegrens in Noord-Amerikaanse datacenters.</span><span class="sxs-lookup"><span data-stu-id="da40c-128">Data from submissions to Microsoft resides in the Office 365 compliance boundary in North American data centers.</span></span> <span data-ttu-id="da40c-129">De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="da40c-129">The data is reviewed by analysts on the engineering team to help improve the effectiveness of the filters.</span></span>
