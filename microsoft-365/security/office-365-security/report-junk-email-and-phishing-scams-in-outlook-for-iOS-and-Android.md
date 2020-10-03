---
title: Ongewenste e-mail en malafide e-mailberichten in Outlook voor iOS en Android melden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie vinden over de ingebouwde opties voor ongewenste e-mail, ongewenste e-mail en het rapporteren van phishing-e-mail in Outlook voor iOS en Android.
ms.openlocfilehash: 23668a762301ee442bc805e62863079ee7ae6076
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350853"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="856de-103">Ongewenste e-mail en malafide e-mailberichten in Outlook voor iOS en Android melden in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="856de-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="856de-104">In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken met [hybride moderne verificatie](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)kunt u de ingebouwde rapportopties in Outlook voor IOS en Android gebruiken voor het verzenden van onjuiste positieven (goede e-mailberichten die als spam zijn gemarkeerd), fout-negatieven (onjuiste e-mail toegestaan) en phishingberichten voor Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="856de-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="856de-105">Wat moet u weten voordat u begint</span><span class="sxs-lookup"><span data-stu-id="856de-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="856de-106">Als u een beheerder bent van een organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="856de-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="856de-107">Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="856de-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="856de-108">U kunt gerapporteerde berichten configureren voor kopiëren of omleiden naar een door u opgegeven postvak.</span><span class="sxs-lookup"><span data-stu-id="856de-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="856de-109">Zie voor meer informatie [beleidsregels voor gebruikers ingediend](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="856de-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="856de-110">Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over het rapporteren van berichten aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="856de-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="856de-111">Als het rapporteren van ongewenste e-mail voor Outlook is uitgeschakeld in het beleid voor het indienen van gebruikers, worden ongewenste e-mail of phishing-berichten verplaatst naar de map Ongewenste E-mail en niet gerapporteerd aan de beheerder of Microsoft.</span><span class="sxs-lookup"><span data-stu-id="856de-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="856de-112">Spamberichten en phishingberichten melden in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="856de-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="856de-113">Voor berichten in het postvak in of een andere e-mailmap met uitzondering van ongewenste E-mail voert u de volgende stappen uit om spam en phishing-berichten te rapporteren voor iOS en Android:</span><span class="sxs-lookup"><span data-stu-id="856de-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="856de-114">Selecteer een of meer berichten.</span><span class="sxs-lookup"><span data-stu-id="856de-114">Select one or more messages.</span></span>
2. <span data-ttu-id="856de-115">Tik in de rechterbovenhoek op de drie verticale stippen.</span><span class="sxs-lookup"><span data-stu-id="856de-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="856de-116">Het actiemenu wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="856de-116">The action menu opens.</span></span>

   ![Ongewenste e-mail of malafide e-mail melden vanuit het menu Actie](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="856de-118">Tik op **Ongewenste E-mail rapporteren** en selecteer vervolgens **ongewenste e-mail** of **phishing**.</span><span class="sxs-lookup"><span data-stu-id="856de-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Ongewenste e-mail of malafide e-mail melden](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="856de-120">In het dialoogvenster dat wordt weergegeven, kunt u op **rapport** of **Nee bedankt**klikken.</span><span class="sxs-lookup"><span data-stu-id="856de-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="856de-121">Als u **geen dank**hebt getikt, **wordt het bericht** naar de map Ongewenste e-mail verplaatst, als **u de map** hebt getikt.</span><span class="sxs-lookup"><span data-stu-id="856de-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="856de-122">Selecteer **rapport** om ook een kopie van het bericht naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="856de-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Rapportageopties voor ongewenste e-mail of malafide e-mail melden](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="856de-124">Als u van gedachten verandert, selecteert u **ongedaan maken** in de pop-upmelding die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="856de-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="856de-125">Het bericht blijft staan in de map Postvak in.</span><span class="sxs-lookup"><span data-stu-id="856de-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="856de-126">Niet-spamberichten rapporteren van de map Ongewenste E-mail in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="856de-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="856de-127">In de map Ongewenste E-mail voert u de volgende stappen uit om spam fout-positieven te rapporteren:</span><span class="sxs-lookup"><span data-stu-id="856de-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="856de-128">Selecteer een of meer berichten.</span><span class="sxs-lookup"><span data-stu-id="856de-128">Select one or more messages.</span></span>
2. <span data-ttu-id="856de-129">Tik in de rechterbovenhoek op de drie verticale stippen.</span><span class="sxs-lookup"><span data-stu-id="856de-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="856de-130">Het actiemenu wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="856de-130">The action menu opens.</span></span>

   ![Geen ongewenste e-mail in het actiemenu rapporteren](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="856de-132">Tik op **geen ongewenste e-mail**.</span><span class="sxs-lookup"><span data-stu-id="856de-132">Tap **Not junk**.</span></span>

<span data-ttu-id="856de-133">Er verschijnt een melding dat het e-mailbericht is verplaatst naar uw postvak in.</span><span class="sxs-lookup"><span data-stu-id="856de-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="856de-134">Als u van gedachten verandert, selecteert u **ongedaan maken** in de pop-upmelding.</span><span class="sxs-lookup"><span data-stu-id="856de-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="856de-135">Het e-mailbericht blijft in de map Ongewenste E-mail staan.</span><span class="sxs-lookup"><span data-stu-id="856de-135">The email remains in the Junk folder.</span></span>
