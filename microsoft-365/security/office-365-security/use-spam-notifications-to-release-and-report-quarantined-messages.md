---
title: Spammeldingen van eindgebruikers in Office 36
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
description: Wanneer een beheerder spammeldingen van eindgebruikers inschakelt in antispambeleid, ontvangen ontvangers van berichten periodieke meldingen over hun in quarantaine geplaatste berichten.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857143"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="cef12-103">Spammeldingen voor eindgebruikers in Office 365</span><span class="sxs-lookup"><span data-stu-id="cef12-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="cef12-104">Quarantaine bevat mogelijk gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="cef12-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="cef12-105">Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cef12-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cef12-106">Spammeldingen van eindgebruikers zijn standaard uitgeschakeld in het antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="cef12-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="cef12-107">Wanneer een beheerder spammeldingen van [eindgebruikers inschakelt,](configure-your-spam-filter-policies.md)ontvangen ontvangers van berichten periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="cef12-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="cef12-108">In oktober 2019 hebben we de mogelijkheid om in quarantaine geplaatste berichten rechtstreeks uit spammeldingen van eindgebruikers vrij te geven, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="cef12-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="cef12-109">In plaats daarvan kunnen gebruikers nu naar het Office 365 Security & Compliance Center gaan om hun berichten in quarantaine vrij te geven (rechtstreeks of door op **Controleren** in de melding te klikken).</span><span class="sxs-lookup"><span data-stu-id="cef12-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="cef12-110">Zie Berichten in [quarantaine zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cef12-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="cef12-111">Berichten die in quarantaine zijn geplaatst als phishing, malware of mailflowregels (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="cef12-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="cef12-112">Zie Berichten in [quarantaine zoeken en vrijgeven als beheerder in Office 365](find-and-release-quarantined-messages-as-an-administrator.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cef12-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="cef12-113">Een spammelding van eindgebruikers bevat de volgende informatie voor elk bericht in quarantaine:</span><span class="sxs-lookup"><span data-stu-id="cef12-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="cef12-114">**Afzender**: De verzendnaam en het e-mailadres van het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="cef12-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="cef12-115">**Onderwerp**: De onderwerpregeltekst van het bericht in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="cef12-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="cef12-116">**Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="cef12-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="cef12-117">**Afzender blokkeren:** Klik op deze koppeling om de afzender toe te voegen aan de lijst Met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="cef12-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="cef12-118">**Review**: Klik op deze link om de quarantaine in het Security & Compliance Center te gaan, waar u uw berichten in quarantaine vrijgeven, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="cef12-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Voorbeeld spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
