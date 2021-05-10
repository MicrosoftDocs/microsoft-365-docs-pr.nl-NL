---
title: Fout-positieven en fout-negatieven rapporteren in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informatie over het rapporteren van onwaar positieven en onwaar negatieven in Outlook met de functie Rapportbericht.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e848595035501f5da7b6099efd2700ebac6f17e3
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291161"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="d50db-103">Fout-positieven en fout-negatieven rapporteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="d50db-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d50db-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d50db-104">**Applies to**</span></span>
- [<span data-ttu-id="d50db-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d50db-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d50db-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d50db-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d50db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d50db-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="d50db-108">Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d50db-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d50db-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d50db-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="d50db-110">In Microsoft 365 organisaties met postvakken in Exchange Online of on-premises postvakken met hybride moderne verificatie, kunt u fout-positieven (goede e-mail die is geblokkeerd of verzonden naar ongewenste map) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) indienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d50db-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d50db-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d50db-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d50db-112">Voor de beste gebruikersinzendingservaring gebruikt u de invoeging Rapportbericht of de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="d50db-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="d50db-113">Houd er rekening mee dat deze invoegtoepassing werkt Outlook op alle platforms: op het web, iOS, Android en desktop.</span><span class="sxs-lookup"><span data-stu-id="d50db-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="d50db-114">Als u een beheerder bent in een organisatie met Exchange Online postvakken, gebruikt u de portal Inzendingen in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d50db-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d50db-115">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d50db-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="d50db-116">U kunt configureren om berichten rechtstreeks naar Microsoft te verzenden, een postvak dat u opgeeft of beide.</span><span class="sxs-lookup"><span data-stu-id="d50db-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="d50db-117">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d50db-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="d50db-118">Zie Het rapportbericht inschakelen of de phishing-invoegvoegingen rapporteren voor meer informatie over het verkrijgen en inschakelen van het rapportbericht of de [phishing-invoegvoegingen.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="d50db-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="d50db-119">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d50db-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="d50db-120">De functie Rapportbericht gebruiken</span><span class="sxs-lookup"><span data-stu-id="d50db-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="d50db-121">Ongewenste e-mailberichten en phishingberichten rapporteren</span><span class="sxs-lookup"><span data-stu-id="d50db-121">Report junk and phishing messages</span></span>

<span data-ttu-id="d50db-122">Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u de volgende methode om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="d50db-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="d50db-123">Klik op **de** drie puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, klik in de vervolgkeuzelijst op Bericht rapporteren en selecteer **vervolgens Ongewenste** e-mail of **Phishing.** </span><span class="sxs-lookup"><span data-stu-id="d50db-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d50db-124">![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d50db-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d50db-125">![Rapportbericht - Ongewenste e-mail en phishing](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="d50db-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="d50db-126">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="d50db-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="d50db-127">Verplaatst naar de map Ongewenste e-mail als deze is gerapporteerd als spam.</span><span class="sxs-lookup"><span data-stu-id="d50db-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="d50db-128">Verwijderd als dit is gerapporteerd als phishing.</span><span class="sxs-lookup"><span data-stu-id="d50db-128">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="d50db-129">Berichten rapporteren die geen ongewenste e-mail zijn</span><span class="sxs-lookup"><span data-stu-id="d50db-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="d50db-130">Klik op **de** drie puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, klik in de vervolgkeuzelijst op Bericht rapporteren en klik vervolgens op **Geen ongewenste e-mail.** </span><span class="sxs-lookup"><span data-stu-id="d50db-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d50db-131">![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d50db-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d50db-132">![Rapportbericht - Geen ongewenste e-mail](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="d50db-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="d50db-133">Het geselecteerde bericht wordt ter analyse naar Microsoft verzonden en verplaatst naar Postvak IN of een andere opgegeven map.</span><span class="sxs-lookup"><span data-stu-id="d50db-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="d50db-134">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="d50db-134">View and review reported messages</span></span>

<span data-ttu-id="d50db-135">Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="d50db-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="d50db-136">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="d50db-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="d50db-137">Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="d50db-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="d50db-138">Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="d50db-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="d50db-139">Zie Regels voor [e-mailstroom gebruiken voor](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)instructies om te zien wat uw gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d50db-139">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>