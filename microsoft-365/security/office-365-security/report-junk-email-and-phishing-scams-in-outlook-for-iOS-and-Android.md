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
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het melden van ongewenste e-mail en phishing in Outlook voor iOS en Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6e63f534a9f9516c6e1a87ff82d5b0916d25778
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509324"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="c35ae-103">Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c35ae-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c35ae-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c35ae-104">**Applies to**</span></span>
- [<span data-ttu-id="c35ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c35ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c35ae-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c35ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c35ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c35ae-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c35ae-108">In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken met hybride [moderne](../../enterprise/hybrid-modern-auth-overview.md)verificatie kunt u fout-positieven (goede e-mail die als spam is gemarkeerd), fout-negatieven (niet-toegestane e-mail) en phishingberichten verzenden naar Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c35ae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c35ae-109">Wat moet u weten voordat u begint</span><span class="sxs-lookup"><span data-stu-id="c35ae-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="c35ae-110">Voor de beste gebruikersverzending wordt u aangeraden het rapportbericht en de phishing-invoegvoegingen te gebruiken. Zie [De invoegapp Bericht rapporteren inschakelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) en [De invoegapp Phishing melden inschakelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c35ae-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="c35ae-111">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="c35ae-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c35ae-112">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="c35ae-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c35ae-113">U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="c35ae-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c35ae-114">Zie beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c35ae-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c35ae-115">Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c35ae-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c35ae-116">Als rapportage van ongewenste e-mail is uitgeschakeld voor Outlook in het beleid voor het indienen van gebruikers, worden ongewenste e-mail of phishingberichten verplaatst naar de map Ongewenste e-mail en niet gerapporteerd aan uw beheerder of Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c35ae-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>
