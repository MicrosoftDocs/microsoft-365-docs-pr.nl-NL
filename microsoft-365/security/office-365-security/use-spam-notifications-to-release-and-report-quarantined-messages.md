---
title: Spammeldingen voor eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 617ff9b6325ac2d5d95d8bc591b9e4ebb7f5434d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921118"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="de769-103">Gebruikersspammeldingen gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren</span><span class="sxs-lookup"><span data-stu-id="de769-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="de769-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="de769-104">**Applies to**</span></span>
- [<span data-ttu-id="de769-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="de769-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="de769-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="de769-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="de769-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de769-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="de769-108">In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst.</span><span class="sxs-lookup"><span data-stu-id="de769-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="de769-109">Zie Berichten in quarantaine plaatsen [in EOP voor meer informatie.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="de769-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="de769-110">Spammeldingen van eindgebruikers worden standaard uitgeschakeld in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="de769-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="de769-111">Wanneer een [beheerder](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)spammeldingen voor eindgebruikers inschakelen, ontvangen geadresseerden (inclusief gedeelde postvakken waarop automatischmapping is ingeschakeld) periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulkmail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="de769-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="de769-112">Voor gedeelde postvakken worden spammeldingen van eindgebruikers alleen ondersteund voor gebruikers die fullaccess-machtigingen krijgen voor het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="de769-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="de769-113">Zie Het EAC gebruiken om gedeelde [postvakdelegering](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)te bewerken voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="de769-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="de769-114">Spammeldingen van eindgebruikers worden niet ondersteund voor groepen.</span><span class="sxs-lookup"><span data-stu-id="de769-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="de769-115">Berichten die in quarantaine zijn geplaatst als phishing, malware of e-mailstroomregels (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="de769-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="de769-116">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="de769-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="de769-117">Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:</span><span class="sxs-lookup"><span data-stu-id="de769-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="de769-118">**Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="de769-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="de769-119">**Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.</span><span class="sxs-lookup"><span data-stu-id="de769-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="de769-120">**Datum:** De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="de769-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="de769-121">**Afzender blokkeren:** Klik op deze koppeling om de afzender toe te voegen aan uw lijst met geblokkeerde afzenders.</span><span class="sxs-lookup"><span data-stu-id="de769-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="de769-122">Zie Een afzender van [e-mail blokkeren voor meer informatie.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)</span><span class="sxs-lookup"><span data-stu-id="de769-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="de769-123">**Release:** Voor spamberichten (geen phishingberichten) kunt u het bericht hier vrijgeven zonder naar het Beveiligingscentrum & quarantaine te gaan.</span><span class="sxs-lookup"><span data-stu-id="de769-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="de769-124">**Controleren:** Klik op deze koppeling om naar Quarantaine te gaan in het beveiligings- & compliancecentrum, waar u (afhankelijk van waarom het bericht in quarantaine is geplaatst) uw in quarantaine geplaatste berichten kunt bekijken, vrijgeven, verwijderen of rapporteren.</span><span class="sxs-lookup"><span data-stu-id="de769-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="de769-125">Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="de769-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="de769-127">Een geblokkeerde afzender kan u nog steeds e-mail sturen.</span><span class="sxs-lookup"><span data-stu-id="de769-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="de769-128">Alle berichten van deze afzender die uw postvak binnen komen, worden onmiddellijk verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="de769-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="de769-129">Toekomstige berichten van deze afzender gaan naar de map Ongewenste e-mail of naar de quarantaine van de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="de769-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="de769-130">Als u deze berichten bij aankomst wilt verwijderen in plaats van ze te quarantineren, gebruikt u regels voor e-mailstroom [(ook](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) wel transportregels genoemd) om de berichten bij aankomst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="de769-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>