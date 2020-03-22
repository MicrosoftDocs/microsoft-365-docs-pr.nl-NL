---
title: Spammeldingen voor eindgebruikers in Office 36
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
description: Wanneer een beheerder spammeldingen van eindgebruikers inantispambeleid inschakelt, ontvangen ontvangers van berichten periodieke meldingen over hun in quarantaine geplaatste berichten.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895057"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="a7f97-103">Spammeldingen voor eindgebruikers in Office 365</span><span class="sxs-lookup"><span data-stu-id="a7f97-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="a7f97-104">Quarantaine bevat potentieel gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="a7f97-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="a7f97-105">Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7f97-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a7f97-106">Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="a7f97-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="a7f97-107">Wanneer een beheerder [spammeldingen van eindgebruikers inschakelt,](configure-your-spam-filter-policies.md)ontvangen ontvangers van berichten periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="a7f97-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="a7f97-108">In oktober 2019 hebben we de mogelijkheid verwijderd om in quarantaine geplaatste berichten rechtstreeks uit spammeldingen van eindgebruikers vrij te geven.</span><span class="sxs-lookup"><span data-stu-id="a7f97-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="a7f97-109">In plaats daarvan kunnen gebruikers nu naar het Office 365 Security & Compliance Center gaan om hun in quarantaine geplaatste berichten vrij te geven (rechtstreeks of door op **Controleren** in de melding te klikken).</span><span class="sxs-lookup"><span data-stu-id="a7f97-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="a7f97-110">Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7f97-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="a7f97-111">Berichten die in quarantaine zijn geplaatst als phishing, malware of door regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="a7f97-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="a7f97-112">Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Office 365](manage-quarantined-messages-and-files.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7f97-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="a7f97-113">Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:</span><span class="sxs-lookup"><span data-stu-id="a7f97-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="a7f97-114">**Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="a7f97-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="a7f97-115">**Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="a7f97-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="a7f97-116">**Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="a7f97-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="a7f97-117">**Afzender blokkeren:** klik op deze koppeling om de afzender toe te voegen aan de lijst Geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="a7f97-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="a7f97-118">**Controle:** Klik op deze koppeling om de quarantaine in het Security & Compliance Center te gaan, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="a7f97-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Voorbeeld van spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
