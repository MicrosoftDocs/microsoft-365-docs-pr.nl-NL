---
title: Spammeldingen van eindgebruikers in Microsoft 365
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
description: Beheerders kunnen informatie krijgen over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: 7dd6b2d14bbb4a1771c59c8a1e654e36f0f83d3e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208547"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="c81a0-103">Spammeldingen van gebruikers gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren</span><span class="sxs-lookup"><span data-stu-id="c81a0-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="c81a0-104">In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, bevat quarantaine potentieel gevaarlijke of ongewenste berichten.</span><span class="sxs-lookup"><span data-stu-id="c81a0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="c81a0-105">Zie [In quarantaine geplaatste berichten in EOP](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c81a0-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="c81a0-106">Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="c81a0-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="c81a0-107">Wanneer een beheerder [spammeldingen van eindgebruikers inschakelt,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ontvangen ontvangers periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="c81a0-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="c81a0-108">Berichten die in quarantaine zijn geplaatst als phishing, malware of door regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="c81a0-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="c81a0-109">Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c81a0-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="c81a0-110">Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:</span><span class="sxs-lookup"><span data-stu-id="c81a0-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="c81a0-111">**Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="c81a0-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="c81a0-112">**Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="c81a0-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="c81a0-113">**Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="c81a0-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="c81a0-114">**Afzender blokkeren:** klik op deze koppeling om de afzender toe te voegen aan de lijst Geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="c81a0-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="c81a0-115">Zie [Een e-mailafzender blokkeren in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c81a0-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="c81a0-116">**Release:** Voor spam (niet phish) berichten, u het bericht hier vrijgeven zonder naar Quarantaine de Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c81a0-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="c81a0-117">**Controle:** Klik op deze link om naar Quarantaine te gaan in het Security & Compliance Center, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="c81a0-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="c81a0-118">Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c81a0-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Voorbeeld van spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
