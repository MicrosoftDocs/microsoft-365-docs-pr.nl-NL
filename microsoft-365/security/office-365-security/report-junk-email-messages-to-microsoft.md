---
title: Spam-, spam- en phishingberichten melden aan Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'De invoegtoepassing Microsoft Voor het melden van ongewenste e-mail voor Microsoft Office Outlook biedt verschillende manieren om ongewenste e-mailberichten te melden:'
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033660"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="900d7-103">Berichten en bestanden rapporteren aan Microsoft</span><span class="sxs-lookup"><span data-stu-id="900d7-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="900d7-104">Gebruikers en beheerders in Office 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken om e-mailberichten in te dienen, hebben verschillende methoden voor het rapporteren van berichten en bestanden naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="900d7-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="900d7-105">**Methode**</span><span class="sxs-lookup"><span data-stu-id="900d7-105">**Method**</span></span>|<span data-ttu-id="900d7-106">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="900d7-106">**Description**</span></span>|
|[<span data-ttu-id="900d7-107">Beheerbeheer gebruiken om vermoedelijke spam, phish, URL's en bestanden bij Microsoft in te dienen</span><span class="sxs-lookup"><span data-stu-id="900d7-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="900d7-108">Dit is de aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP).</span><span class="sxs-lookup"><span data-stu-id="900d7-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="900d7-109">De invoegtoepassing Rapportbericht inschakelen in Office 365</span><span class="sxs-lookup"><span data-stu-id="900d7-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="900d7-110">Werkt met Outlook, Outlook voor Mac en de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="900d7-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="900d7-111">Dit is de aanbevolen invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="900d7-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="900d7-112">Afhankelijk van uw licentie zijn de gerapporteerde berichten beschikbaar in [de resultaten van Automated Investigation and Response (AIR),](air-view-investigation-results.md)het door de gebruiker [gerapporteerde berichtenrapport](view-email-security-reports.md#user-reported-messages-report) en [Threat Explorer.](threat-explorer-views.md#email--submissions)</span><span class="sxs-lookup"><span data-stu-id="900d7-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="900d7-113">De invoegtoepassing Voor melding van ongewenste e-mail rapportage voor Microsoft Outlook installeren en gebruiken in Office 365</span><span class="sxs-lookup"><span data-stu-id="900d7-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="900d7-114">Werkt alleen in Outlook.</span><span class="sxs-lookup"><span data-stu-id="900d7-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="900d7-115">Ongewenste en phishing-e-mail melden in de webversie van Outlook in Office 365</span><span class="sxs-lookup"><span data-stu-id="900d7-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="900d7-116">Gebruik de ingebouwde mogelijkheden in de webversie van Outlook voor organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP).</span><span class="sxs-lookup"><span data-stu-id="900d7-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="900d7-117">Malware en niet-malware indienen bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="900d7-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="900d7-118">Gebruik de Microsoft Security Intelligence-site om bijlagen en andere bestanden in te dienen.</span><span class="sxs-lookup"><span data-stu-id="900d7-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="900d7-119">Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van geleverd, kunnen gebruikers de berichten aan Microsoft rapporteren vanuit de quarantaineportal in het Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="900d7-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="900d7-120">Zie In [quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="900d7-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>