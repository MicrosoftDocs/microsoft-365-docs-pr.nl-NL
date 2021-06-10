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
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789241"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="e650d-103">Fout-positieven en fout-negatieven rapporteren in Outlook</span><span class="sxs-lookup"><span data-stu-id="e650d-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e650d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e650d-104">**Applies to**</span></span>
- [<span data-ttu-id="e650d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e650d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e650d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e650d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e650d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e650d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e650d-108">Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="e650d-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e650d-109">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e650d-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e650d-110">In Microsoft 365 organisaties met postvakken in Exchange Online of on-premises postvakken met hybride moderne verificatie, kunt u fout-positieven (goede e-mail die is geblokkeerd of verzonden naar ongewenste map) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) indienen bij Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e650d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e650d-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="e650d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e650d-112">Voor de beste gebruikersinzendingservaring gebruikt u de invoeging Rapportbericht of de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="e650d-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e650d-113">De ingebouwde ervaring voor het melden van ongewenste e-mail of phishing in Outlook kan geen gebruik maken van het beleid voor het indienen [van gebruikers.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e650d-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="e650d-114">We raden u aan in plaats daarvan de invoeging Rapportbericht of de invoeging Phishing melden te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e650d-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="e650d-115">De invoegtoepassing Rapportbericht en de invoegtoepassing Phishing melden werken voor Outlook op alle platforms (Outlook op het web, iOS, Android en desktop).</span><span class="sxs-lookup"><span data-stu-id="e650d-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="e650d-116">Als u een beheerder bent in een organisatie met Exchange Online postvakken, gebruikt u de portal Inzendingen in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="e650d-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e650d-117">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e650d-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="e650d-118">U kunt configureren om berichten rechtstreeks naar Microsoft te verzenden, een postvak dat u opgeeft of beide.</span><span class="sxs-lookup"><span data-stu-id="e650d-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="e650d-119">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e650d-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e650d-120">Zie Het rapportbericht inschakelen of de phishing-invoegvoegingen rapporteren voor meer informatie over het verkrijgen en inschakelen van het rapportbericht of de [phishing-invoegvoegingen.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="e650d-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="e650d-121">Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e650d-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="e650d-122">De functie Rapportbericht gebruiken</span><span class="sxs-lookup"><span data-stu-id="e650d-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="e650d-123">Ongewenste e-mailberichten en phishingberichten rapporteren</span><span class="sxs-lookup"><span data-stu-id="e650d-123">Report junk and phishing messages</span></span>

<span data-ttu-id="e650d-124">Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u de volgende methode om spam- en phishingberichten te melden:</span><span class="sxs-lookup"><span data-stu-id="e650d-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="e650d-125">Selecteer de **puntjes** Meer acties in de rechterbovenhoek van het geselecteerde bericht, selecteer **Bericht** rapporteren in de vervolgkeuzelijst en selecteer vervolgens **Ongewenste** e-mail of **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="e650d-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)
   
   ![Rapportbericht - Ongewenste e-mail en phishing](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="e650d-128">De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:</span><span class="sxs-lookup"><span data-stu-id="e650d-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="e650d-129">Verplaatst naar de map Ongewenste e-mail als ze als spam zijn gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e650d-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="e650d-130">Verwijderd als ze als phishing zijn gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e650d-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="e650d-131">Berichten rapporteren die geen ongewenste e-mail zijn</span><span class="sxs-lookup"><span data-stu-id="e650d-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="e650d-132">Selecteer de **drie** puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, selecteer **Bericht** rapporteren in de vervolgkeuzelijst en selecteer **vervolgens Geen ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="e650d-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)
   
   ![Rapportbericht - Geen ongewenste e-mail](../../media/report-message-not-junk.png)

2. <span data-ttu-id="e650d-135">Het geselecteerde bericht wordt ter analyse naar Microsoft verzonden en verplaatst naar Postvak IN of een andere opgegeven map.</span><span class="sxs-lookup"><span data-stu-id="e650d-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="e650d-136">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="e650d-136">View and review reported messages</span></span>

<span data-ttu-id="e650d-137">Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="e650d-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="e650d-138">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="e650d-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="e650d-139">Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="e650d-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="e650d-140">Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="e650d-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="e650d-141">Zie Regels voor [e-mailstroom gebruiken voor](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)instructies om te zien wat gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e650d-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
