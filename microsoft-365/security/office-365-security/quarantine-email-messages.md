---
title: Quarantaine in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Quarantaine in Office 365 bevat potentieel gevaarlijke of ongewenste berichten. Beheerders en eindgebruikers hebben toegang tot quarantaine.
ms.openlocfilehash: a11b4a0d86cfc5f74636d3a9f89cf598320d1ebf
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2020
ms.locfileid: "42940955"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="062e8-104">Quarantaine in Office 365</span><span class="sxs-lookup"><span data-stu-id="062e8-104">Quarantine in Office 365</span></span>

<span data-ttu-id="062e8-105">Als u een Office 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection-klant (EOP) zonder Exchange Online-postvakken, is quarantaine beschikbaar om potentieel gevaarlijke of ongewenste berichten vast te houden.</span><span class="sxs-lookup"><span data-stu-id="062e8-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="062e8-106">Anti-malwarebeleid plaatst een bericht automatisch in quarantaine als *blijkt dat er* een bijlage is die malware bevat.</span><span class="sxs-lookup"><span data-stu-id="062e8-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="062e8-107">Zie [Beleid voor antimalware configureren in Office 365](configure-anti-malware-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="062e8-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="062e8-108">Standaard worden phishingberichten in quarantaine geplaatst en worden spam- en bulk-e-mailberichten verzonden naar de map Ongewenste e-mail van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="062e8-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="062e8-109">U echter ook antispambeleid maken en aanpassen om spam en bulk-e-mailberichten in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="062e8-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="062e8-110">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="062e8-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="062e8-111">Zowel gebruikers als beheerders kunnen werken met in quarantaine geplaatste berichten:</span><span class="sxs-lookup"><span data-stu-id="062e8-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="062e8-112">Beheerders kunnen werken met alle soorten in quarantaine geplaatste berichten voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="062e8-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="062e8-113">Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="062e8-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="062e8-114">Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="062e8-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="062e8-115">Gebruikers kunnen werken met in quarantaine geplaatste berichten waar ze een ontvanger zijn als het bericht in quarantaine is geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="062e8-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="062e8-116">Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="062e8-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="062e8-117">Om te voorkomen dat gebruikers hun eigen phishingberichten in quarantaine beheren, kunnen beheerders een andere actie configureren voor het **phishing-e-mailfiltervonnis** in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="062e8-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="062e8-118">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="062e8-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="062e8-119">Beheerders en gebruikers kunnen valse positieven melden aan Microsoft in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="062e8-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="062e8-120">Zie [Veelgestelde vragen](quarantine-faq.md)over quarantaine voor meer informatie over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="062e8-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
