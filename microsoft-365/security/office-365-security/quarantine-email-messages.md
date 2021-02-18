---
title: E-mailberichten in quarantaine
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
description: Beheerders kunnen meer te weten komen over quarantaine in Exchange Online Protection (EOP) die mogelijk gevaarlijke of ongewenste berichten bevat.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288763"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="27954-103">E-mailberichten in quarantaine in EOP</span><span class="sxs-lookup"><span data-stu-id="27954-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="27954-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="27954-104">**Applies to**</span></span>
- [<span data-ttu-id="27954-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27954-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="27954-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="27954-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="27954-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27954-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="27954-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken is quarantaine beschikbaar voor het plaatsen van mogelijk gevaarlijke of ongewenste berichten.</span><span class="sxs-lookup"><span data-stu-id="27954-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="27954-109">Een bericht wordt automatisch in  quarantaine geplaatst als malware wordt aangetroffen bij bijlagen.</span><span class="sxs-lookup"><span data-stu-id="27954-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="27954-110">Zie [Antimalwarebeleid](configure-anti-malware-policies.md)configureren in EOP voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="27954-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="27954-111">Standaard worden phishingberichten in quarantaine tegen ongewenste e-mail in quarantaine geplaatst en worden spam en bulk-e-mailberichten naar de map Ongewenste e-mail van de gebruiker verzonden.</span><span class="sxs-lookup"><span data-stu-id="27954-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="27954-112">Maar u kunt ook antispambeleid maken en aanpassen voor spam en bulk-e-mailberichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="27954-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="27954-113">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="27954-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="27954-114">Zowel gebruikers als beheerders kunnen met in quarantaine geplaatste berichten werken:</span><span class="sxs-lookup"><span data-stu-id="27954-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="27954-115">Beheerders kunnen werken met alle typen berichten in quarantaine voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="27954-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="27954-116">Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, zeer vertrouwelijk phishing of als gevolg van regels voor de e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="27954-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="27954-117">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="27954-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="27954-118">Gebruikers kunnen in quarantaine geplaatste berichten plaatsen waar ze geadresseerden zijn als het bericht in quarantaine is geplaatst als spam, bulk-e-mail of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="27954-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="27954-119">Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="27954-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="27954-120">Beheerders kunnen voorkomen dat gebruikers hun eigen phishingberichten in quarantaine  beheren door een andere actie te configureren voor het filteren van Phishing-e-mails in antispambeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="27954-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="27954-121">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="27954-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="27954-122">Beheerders en gebruikers kunnen fout-positieven rapporteren aan Microsoft in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="27954-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="27954-123">Zie veelgestelde vragen over [quarantaine](quarantine-faq.md)voor meer informatie over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="27954-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
