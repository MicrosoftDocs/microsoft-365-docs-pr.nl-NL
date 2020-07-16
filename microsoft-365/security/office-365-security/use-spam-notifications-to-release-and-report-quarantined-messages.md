---
title: Spammeldingen voor eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: 14dcdfa8373e3826b23bc5574d1b5ae8ff76927b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754782"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="098f3-103">Spammeldingen van gebruikers gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren</span><span class="sxs-lookup"><span data-stu-id="098f3-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="098f3-104">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="098f3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="098f3-105">Zie [In quarantaine geplaatste berichten in EOP](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="098f3-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="098f3-106">Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="098f3-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="098f3-107">Wanneer een beheerder [spammeldingen voor eindgebruikers inschakelt,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ontvangen ontvangers (inclusief gedeelde postvakken) periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="098f3-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="098f3-108">Berichten die in quarantaine zijn geplaatst als phishing met een hoog vertrouwen, malware of via regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="098f3-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="098f3-109">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="098f3-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="098f3-110">Een spammelding voor eindgebruikers bevat de volgende informatie voor elk bericht in quarantaine:</span><span class="sxs-lookup"><span data-stu-id="098f3-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="098f3-111">**Afzender**: de verzendnaam en het e-mailadres van het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="098f3-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="098f3-112">**Onderwerp**: De onderwerpregeltekst van het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="098f3-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="098f3-113">**Datum**: de datum en tijd (in UTC) waarop het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="098f3-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="098f3-114">**Afzender blokkeren**: klik op deze koppeling om de afzender toe te voegen aan de lijst Met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="098f3-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="098f3-115">Zie [Een afzender van een e-mail blokkeren voor](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="098f3-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="098f3-116">**Release:** Voor spamberichten (geen phish) berichten u het bericht hier vrijgeven zonder het Security & Compliance Center in quarantaine te gaan.</span><span class="sxs-lookup"><span data-stu-id="098f3-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="098f3-117">**Review**: Klik op deze link om naar Quarantaine te gaan in het Security & Compliance Center, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="098f3-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="098f3-118">Zie [Berichten zoeken en vrijgeven als gebruiker in EOP voor](find-and-release-quarantined-messages-as-a-user.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="098f3-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)
