---
title: Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het rapporteren van ongewenste e-mail, geen ongewenste e-mail en phishing-e-mail in Outlook voor iOS en Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166817"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="fdfeb-103">Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fdfeb-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fdfeb-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="fdfeb-104">**Applies to**</span></span>
- [<span data-ttu-id="fdfeb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fdfeb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="fdfeb-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="fdfeb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="fdfeb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fdfeb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fdfeb-108">In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken die gebruikmaken van hybride [moderne](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)verificatie, kunt u de ingebouwde rapportageopties in Outlook voor iOS en Android gebruiken om fout-positieven (goede e-mail gemarkeerd als spam), fout-negatieven (slechte e-mail toegestaan) en phishingberichten naar Exchange Online Protection (EOP) te verzenden.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fdfeb-109">Wat moet u weten voordat u begint</span><span class="sxs-lookup"><span data-stu-id="fdfeb-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="fdfeb-110">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="fdfeb-111">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="fdfeb-112">U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="fdfeb-113">Zie beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="fdfeb-114">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="fdfeb-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fdfeb-115">Als rapportage van ongewenste e-mail is uitgeschakeld voor Outlook in het beleid voor het indienen van gebruikers, worden ongewenste e-mail of phishingberichten verplaatst naar de map Ongewenste e-mail en niet gerapporteerd aan uw beheerder of Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="fdfeb-116">Spam en phishingberichten rapporteren in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="fdfeb-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="fdfeb-117">Gebruik de volgende stappen voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, om spam- en phishingberichten te melden voor iOS en Android:</span><span class="sxs-lookup"><span data-stu-id="fdfeb-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="fdfeb-118">Selecteer een of meer berichten.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-118">Select one or more messages.</span></span>
2. <span data-ttu-id="fdfeb-119">Tik in de rechterbovenhoek op de drie verticale puntjes.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="fdfeb-120">Het actiemenu wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-120">The action menu opens.</span></span>

   ![Ongewenste e-mail of phishing-e-mail melden via het actiemenu](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="fdfeb-122">Tik **op Ongewenste e-mail** melden en selecteer **vervolgens Ongewenste e-mail** of **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="fdfeb-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Ongewenste e-mail of phishing-e-mail melden](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="fdfeb-124">In het dialoogvenster dat wordt weergegeven, kunt u **Rapport** of **Nee, bedankt kiezen.**</span><span class="sxs-lookup"><span data-stu-id="fdfeb-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="fdfeb-125">Als u **Op Ongewenste** e-mail hebt getikt, wordt het verplaatst naar de map Ongewenste e-mail als u op Phishing hebt getikt. Als u op **Phishing** hebt getikt, wordt het bericht verplaatst naar de map Verwijderde items. </span><span class="sxs-lookup"><span data-stu-id="fdfeb-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="fdfeb-126">Selecteer **Rapport** om ook een kopie van het bericht naar Microsoft te verzenden.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Opties voor rapportage van ongewenste e-mail of phishing-e-mail rapporteren](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="fdfeb-128">Als u van gedachten verandert, **selecteert** u Ongedaan maken in de pop-upmelding die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="fdfeb-129">Het bericht blijft in de map Postvak IN staan.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="fdfeb-130">Niet-spamberichten rapporteren vanuit de map Ongewenste e-mail in Outlook voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="fdfeb-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="fdfeb-131">Gebruik in de map Ongewenste e-mail de volgende stappen om fout-positieven over spam te melden:</span><span class="sxs-lookup"><span data-stu-id="fdfeb-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="fdfeb-132">Selecteer een of meer berichten.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-132">Select one or more messages.</span></span>
2. <span data-ttu-id="fdfeb-133">Tik in de rechterbovenhoek op de drie verticale puntjes.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="fdfeb-134">Het actiemenu wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-134">The action menu opens.</span></span>

   ![Geen ongewenste e-mail rapporteren via het actiemenu](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="fdfeb-136">Tik **op Geen ongewenste e-mail.**</span><span class="sxs-lookup"><span data-stu-id="fdfeb-136">Tap **Not junk**.</span></span>

<span data-ttu-id="fdfeb-137">Er wordt een pop-upmelding weergegeven dat het e-mailbericht naar uw Postvak IN is verplaatst.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="fdfeb-138">Als u van gedachten verandert, **selecteert** u Ongedaan maken in de pop-upmelding.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="fdfeb-139">De e-mail blijft in de map Ongewenste e-mail staan.</span><span class="sxs-lookup"><span data-stu-id="fdfeb-139">The email remains in the Junk folder.</span></span>
