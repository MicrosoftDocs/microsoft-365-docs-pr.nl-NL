---
title: Spam meldingen voor eindgebruikers in Microsoft 365
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
description: Beheerders kunnen informatie lezen over spam meldingen voor eindgebruikers voor berichten in quarantaine in Exchange Online Protection (EOP).
ms.openlocfilehash: 2786c90f6f5fb66cbb96b0375dacf7793894f72e
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778502"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="f0365-103">Gebruik spam meldingen van gebruikers om berichten in quarantaine vrij te geven en te rapporteren</span><span class="sxs-lookup"><span data-stu-id="f0365-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="f0365-104">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="f0365-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="f0365-105">Zie voor meer informatie [quarantaine berichten in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f0365-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="f0365-106">Standaard zijn meldingen voor spam van eindgebruikers uitgeschakeld in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="f0365-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="f0365-107">Wanneer een beheerder [meldingen voor spam van eindgebruikers](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)uitschakelt, ontvangen geadresseerden (inclusief gedeelde postvakken met automatisch toewijzen ingeschakeld) periodieke meldingen over hun berichten die zijn gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="f0365-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="f0365-108">Voor gedeelde postvakken worden meldingen voor spam van eindgebruikers alleen ondersteund voor gebruikers aan wie de machtiging machtiging fullaccess is verleend voor het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="f0365-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="f0365-109">Zie voor meer informatie [gedeeld postvak delegering bewerken](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="f0365-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="f0365-110">Spam melding voor eindgebruikers wordt niet ondersteund voor groepen.</span><span class="sxs-lookup"><span data-stu-id="f0365-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="f0365-111">Berichten die zijn gequarantined als phishing van hoge betrouwbaarheid, malware of via e-mail stroom regels (ook wel bekend als transportregels), zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="f0365-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="f0365-112">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="f0365-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="f0365-113">Een melding voor spam van eindgebruikers bevat de volgende informatie voor elk gequarantine bericht:</span><span class="sxs-lookup"><span data-stu-id="f0365-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="f0365-114">**Afzender**: de naam en het e-mailadres van het gequarantinede bericht verzenden.</span><span class="sxs-lookup"><span data-stu-id="f0365-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="f0365-115">**Onderwerp**: het onderwerp van de tekst van het bericht in de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="f0365-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="f0365-116">**Datum**: de datum en tijd (in UTC) waarop het bericht is in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="f0365-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="f0365-117">**Afzender blokkeren**: Klik op deze link om de afzender toe te voegen aan uw lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="f0365-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="f0365-118">Zie voor meer informatie [de afzender van een e-mailbericht blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="f0365-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="f0365-119">**Release**: voor spamberichten (niet voor phishing), kunt u het bericht hier vrijgeven zonder dat u de beveiliging voor de beveiliging & Quarantine.</span><span class="sxs-lookup"><span data-stu-id="f0365-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="f0365-120">**Controleren**: Klik op deze koppeling om naar Quarantine te gaan in het beveiligings & nalevings centrum, waarin u kunt zien welke berichten in quarantaine zijn geplaatst, of laat zien, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="f0365-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="f0365-121">Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f0365-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Voorbeeld van spam met eindgebruikers](../../media/end-user-spam-notification.png)
