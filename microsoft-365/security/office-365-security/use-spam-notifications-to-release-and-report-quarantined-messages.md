---
title: Spam meldingen voor eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600295"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="0cc01-103">Gebruik spam meldingen van gebruikers om berichten in quarantaine vrij te geven en te rapporteren</span><span class="sxs-lookup"><span data-stu-id="0cc01-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0cc01-104">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="0cc01-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="0cc01-105">Zie voor meer informatie [quarantaine berichten in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="0cc01-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="0cc01-106">Standaard zijn meldingen voor spam van eindgebruikers uitgeschakeld in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="0cc01-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="0cc01-107">Wanneer een beheerder [meldingen voor spam van eindgebruikers](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)uitschakelt, ontvangen geadresseerden (inclusief gedeelde postvakken met automatisch toewijzen ingeschakeld) periodieke meldingen over hun berichten die zijn gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="0cc01-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="0cc01-108">Voor gedeelde postvakken worden meldingen voor spam van eindgebruikers alleen ondersteund voor gebruikers aan wie de machtiging machtiging fullaccess is verleend voor het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="0cc01-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="0cc01-109">Zie voor meer informatie [gedeeld postvak delegering bewerken](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="0cc01-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="0cc01-110">Spam melding voor eindgebruikers wordt niet ondersteund voor groepen.</span><span class="sxs-lookup"><span data-stu-id="0cc01-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="0cc01-111">Berichten die zijn gequarantined als phishing van hoge betrouwbaarheid, malware of via e-mail stroom regels (ook wel bekend als transportregels), zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="0cc01-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="0cc01-112">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="0cc01-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="0cc01-113">Een melding voor spam van eindgebruikers bevat de volgende informatie voor elk gequarantine bericht:</span><span class="sxs-lookup"><span data-stu-id="0cc01-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="0cc01-114">**Afzender**: de naam en het e-mailadres van het gequarantinede bericht verzenden.</span><span class="sxs-lookup"><span data-stu-id="0cc01-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="0cc01-115">**Onderwerp**: het onderwerp van de tekst van het bericht in de quarantaine.</span><span class="sxs-lookup"><span data-stu-id="0cc01-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="0cc01-116">**Datum**: de datum en tijd (in UTC) waarop het bericht is in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="0cc01-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="0cc01-117">**Afzender blokkeren**: Klik op deze link om de afzender toe te voegen aan uw lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="0cc01-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="0cc01-118">Zie voor meer informatie [de afzender van een e-mailbericht blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="0cc01-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="0cc01-119">**Release**: voor spamberichten (niet voor phishing), kunt u het bericht hier vrijgeven zonder dat u de beveiliging voor de beveiliging & Quarantine.</span><span class="sxs-lookup"><span data-stu-id="0cc01-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="0cc01-120">**Controleren**: Klik op deze koppeling om naar Quarantine te gaan in het beveiligings & nalevings centrum, waarin u kunt zien welke berichten in quarantaine zijn geplaatst, of laat zien, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="0cc01-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="0cc01-121">Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="0cc01-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Voorbeeld van spam met eindgebruikers](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="0cc01-123">Een geblokkeerde afzender kan nog steeds e-mail verzenden.</span><span class="sxs-lookup"><span data-stu-id="0cc01-123">A blocked sender can still send you mail.</span></span> <span data-ttu-id="0cc01-124">Berichten van deze afzender die de afzender maken in uw postvak, worden direct verplaatst naar de map Ongewenste E-mail.</span><span class="sxs-lookup"><span data-stu-id="0cc01-124">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="0cc01-125">Toekomstige berichten van deze afzender worden verzonden naar de map Ongewenste E-mail of naar de Quarantine voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="0cc01-125">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="0cc01-126">Als u deze berichten op aankomst wilt verwijderen in plaats van ze te quarantining, gebruikt u [regels voor e-mail stroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transport-regels genoemd) om berichten bij de ontvangst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0cc01-126">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>
