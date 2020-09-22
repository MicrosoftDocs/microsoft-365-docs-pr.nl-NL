---
title: Gequarantinede e-mailberichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over quarantaine in Exchange Online Protection (EOP) die mogelijk schadelijke of ongewenste berichten bevat.
ms.openlocfilehash: 77eea3140fb96faec4fb5a749422c2bd9da85b45
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202469"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="bae10-103">Gequarantinede e-mailberichten in EOP</span><span class="sxs-lookup"><span data-stu-id="bae10-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bae10-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvak in van Exchange</span><span class="sxs-lookup"><span data-stu-id="bae10-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="bae10-105">Beleidsregels voor malware die een bericht met malware *tegenkomen.*</span><span class="sxs-lookup"><span data-stu-id="bae10-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="bae10-106">Zie voor meer informatie [anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bae10-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="bae10-107">Standaard wordt in antispam voor de gebruiker in de map Ongewenste E-mail in de map Ongewenste E-mail gebruikt om spamberichten te ontvangen en spam en bulk-e-mailberichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="bae10-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="bae10-108">U kunt ook Antispambeleid maken en aanpassen voor het Quarantine spam en bulk-e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="bae10-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="bae10-109">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bae10-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bae10-110">Gebruikers en beheerders kunnen werken met berichten in quarantaine:</span><span class="sxs-lookup"><span data-stu-id="bae10-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="bae10-111">Beheerders kunnen werken met alle typen quarantaine berichten voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bae10-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="bae10-112">Alleen beheerders kunnen werken met berichten die zijn gequarantined als malware, phishing van hoge betrouwbaarheid of als gevolg van de regels voor de e-mail stroom (ook wel een transportregel genoemd).</span><span class="sxs-lookup"><span data-stu-id="bae10-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="bae10-113">Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bae10-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="bae10-114">Gebruikers kunnen werken met berichten in quarantaine waarvan ze een geadresseerde zijn als het bericht is gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="bae10-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="bae10-115">Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bae10-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="bae10-116">Om te voorkomen dat gebruikers hun eigen verplaatste phishingberichten kunnen beheren, kunnen beheerders een andere actie voor het filteren van **e-mail** berichten verdict in Antispambeleid configureren.</span><span class="sxs-lookup"><span data-stu-id="bae10-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="bae10-117">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bae10-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="bae10-118">Beheerders en gebruikers kunnen fout-positieven rapporteren aan Microsoft in Quarantine.</span><span class="sxs-lookup"><span data-stu-id="bae10-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="bae10-119">Zie [Veelgestelde vragen over quarantaine](quarantine-faq.md)voor meer informatie over quarantaine.</span><span class="sxs-lookup"><span data-stu-id="bae10-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
