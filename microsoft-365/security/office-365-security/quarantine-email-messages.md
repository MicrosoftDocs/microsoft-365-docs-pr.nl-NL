---
title: In quarantaine geplaatste e-mailberichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over quarantaine in Exchange Online Protection (EOP) die potentieel gevaarlijke of ongewenste berichten bevat.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a11f5f9e1e730a3b0cc09625ec8e8cb592d869
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333804"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="c4c25-103">In quarantaine geplaatste e-mailberichten in EOP</span><span class="sxs-lookup"><span data-stu-id="c4c25-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4c25-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c4c25-104">**Applies to**</span></span>
- [<span data-ttu-id="c4c25-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c4c25-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c4c25-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c4c25-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c4c25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4c25-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c4c25-108">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken is quarantaine beschikbaar voor het vasthouden van potentieel gevaarlijke of ongewenste berichten.</span><span class="sxs-lookup"><span data-stu-id="c4c25-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="c4c25-109">Anti-malwarebeleid zet een bericht automatisch in quarantaine als *een* bijlage malware bevat.</span><span class="sxs-lookup"><span data-stu-id="c4c25-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="c4c25-110">Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4c25-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="c4c25-111">Antispam polices quarantaine phishingberichten standaard, en leveren spam en bulk-e-mailberichten aan de map Ongewenste e-mail van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c4c25-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="c4c25-112">Maar u kunt ook antispambeleid maken en aanpassen om spam en bulk-e-mailberichten in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="c4c25-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="c4c25-113">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4c25-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c4c25-114">Zowel gebruikers als beheerders kunnen werken met in quarantaine geplaatste berichten:</span><span class="sxs-lookup"><span data-stu-id="c4c25-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="c4c25-115">Beheerders kunnen werken met alle typen in quarantaine geplaatste berichten voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c4c25-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="c4c25-116">Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, phishing met hoge betrouwbaarheid of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="c4c25-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c4c25-117">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c4c25-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="c4c25-118">Gebruikers kunnen werken met in quarantaine geplaatste berichten waar ze een geadresseerde zijn als het bericht in quarantaine is geplaatst als spam, bulk-e-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="c4c25-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="c4c25-119">Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4c25-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="c4c25-120">Om te voorkomen dat gebruikers hun eigen in quarantaine geplaatste phishingberichten beheren, kunnen beheerders een andere actie configureren voor het **filteren** van phishing-e-mail in antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="c4c25-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c4c25-121">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4c25-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="c4c25-122">Beheerders en gebruikers kunnen fout-positieven melden bij Microsoft in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="c4c25-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="c4c25-123">Zie Veelgestelde vragen over quarantaine voor [meer informatie](quarantine-faq.yml)over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="c4c25-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.yml).</span></span>
