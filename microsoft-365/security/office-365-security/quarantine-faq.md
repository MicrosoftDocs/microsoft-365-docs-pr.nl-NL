---
title: Veelgestelde vragen over in quarantaine geplaatste berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Beheerders kunnen veelgestelde vragen en antwoorden over in quarantaine geplaatste berichten bekijken in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a231e363d5764465547ee1e80cc080c3d7c006c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351093"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="1e77e-103">Veelgestelde vragen over in quarantaine geplaatste berichten</span><span class="sxs-lookup"><span data-stu-id="1e77e-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="1e77e-104">In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over in quarantaine geplaatste e-mailberichten voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="1e77e-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="1e77e-105">Zie [Veelgestelde vragen](anti-spam-protection-faq.md)over spambescherming voor vragen en antwoorden over bescherming tegen spam.</span><span class="sxs-lookup"><span data-stu-id="1e77e-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="1e77e-106">Zie [Veelgestelde vragen](anti-malware-protection-faq-eop.md)over bescherming tegen malware voor vragen en antwoorden over bescherming tegen malware.</span><span class="sxs-lookup"><span data-stu-id="1e77e-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="1e77e-107">Zie Veelgestelde vragen over [anti-spoofing bescherming](anti-spoofing-protection-faq.md)voor vragen en antwoorden over anti-spoofing bescherming.</span><span class="sxs-lookup"><span data-stu-id="1e77e-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="1e77e-108">Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?</span><span class="sxs-lookup"><span data-stu-id="1e77e-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="1e77e-109">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware.</span><span class="sxs-lookup"><span data-stu-id="1e77e-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="1e77e-110">Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder voor](manage-quarantined-messages-and-files.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1e77e-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="1e77e-111">Hoe quarantaine spam?</span><span class="sxs-lookup"><span data-stu-id="1e77e-111">How do I quarantine spam?</span></span>

<span data-ttu-id="1e77e-112">Berichten die door spamfilter worden geclassificeerd als spam of bulk-e-mail worden standaard naar het postvak van de gebruiker verzonden en worden verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="1e77e-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="1e77e-113">Maar u in plaats daarvan antispambeleid maken en configureren om spam of bulke-mailberichten in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="1e77e-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="1e77e-114">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1e77e-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="1e77e-115">Hoe geef ik gebruikers toegang tot de quarantaine?</span><span class="sxs-lookup"><span data-stu-id="1e77e-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="1e77e-116">Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn eigen berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="1e77e-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="1e77e-117">Standalone EOP vereist dat gebruikers worden vertegenwoordigd als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie).</span><span class="sxs-lookup"><span data-stu-id="1e77e-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="1e77e-118">Zie [E-mailgebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="1e77e-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="1e77e-119">Welke berichten kunnen eindgebruikers in quarantaine openen?</span><span class="sxs-lookup"><span data-stu-id="1e77e-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="1e77e-120">Gebruikers hebben toegang tot spam, bulke-mail en (vanaf april 2020) phishingberichten waar ze een ontvanger zijn.</span><span class="sxs-lookup"><span data-stu-id="1e77e-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="1e77e-121">Eindgebruikers hebben geen toegang tot in quarantaine geplaatste malware, phishing met een hoog vertrouwen of berichten die in quarantaine zijn geplaatst vanwege de **actie Het bericht leveren aan de gehoste quarantaineactie** in de regels voor e-mailstromen (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="1e77e-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1e77e-122">Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker voor](find-and-release-quarantined-messages-as-a-user.md)meer informatie over gebruikers die toegang hebben tot in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="1e77e-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="1e77e-123">Hoe lang worden berichten in quarantaine gehouden?</span><span class="sxs-lookup"><span data-stu-id="1e77e-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="1e77e-124">U configureert hoe lang spam- en phishing- en bulke-mailberichten in quarantaine worden gehouden met behulp van antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="1e77e-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="1e77e-125">De standaard instelling is 30 dagen, wat ook het maximum is.</span><span class="sxs-lookup"><span data-stu-id="1e77e-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="1e77e-126">Zie [Beleid voor antispam configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="1e77e-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="1e77e-127">Voor berichten die in quarantaine zijn geplaatst door de regelactie E-mailstroom **Breng het bericht naar de gehoste quarantaine,** worden de berichten 30 dagen in quarantaine gehouden.</span><span class="sxs-lookup"><span data-stu-id="1e77e-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="1e77e-128">U deze duur niet configureren.</span><span class="sxs-lookup"><span data-stu-id="1e77e-128">You can't configure this duration.</span></span>

<span data-ttu-id="1e77e-129">Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="1e77e-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="1e77e-130">Kan ik meerdere in quarantaine geplaatste berichten tegelijk vrijgeven of rapporteren?</span><span class="sxs-lookup"><span data-stu-id="1e77e-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="1e77e-131">In het Security & Compliance Center u maximaal 100 berichten tegelijk selecteren en vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="1e77e-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="1e77e-132">Beheerders kunnen de cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) en [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) gebruiken in Exchange Online PowerShell of standalone EOP PowerShell om in bulk in quarantaine geplaatste berichten te vinden en vrij te geven en om valse positieven in bulk te melden.</span><span class="sxs-lookup"><span data-stu-id="1e77e-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="1e77e-133">Worden wildcards ondersteund bij het zoeken naar in quarantaine geplaatste berichten?</span><span class="sxs-lookup"><span data-stu-id="1e77e-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="1e77e-134">Kan ik zoeken naar in quarantaine geplaatste berichten voor een specifiek domein?</span><span class="sxs-lookup"><span data-stu-id="1e77e-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="1e77e-135">Jokertekens worden niet ondersteund in het Beveiligingscentrum & Compliance.</span><span class="sxs-lookup"><span data-stu-id="1e77e-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="1e77e-136">Wanneer u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven.</span><span class="sxs-lookup"><span data-stu-id="1e77e-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="1e77e-137">Maar u wildcards gebruiken in Exchange Online PowerShell of standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e77e-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="1e77e-138">Voer bijvoorbeeld de volgende opdracht uit om spamin quarantaine geplaatste berichten van alle afzenders in het domein contoso.com te vinden:</span><span class="sxs-lookup"><span data-stu-id="1e77e-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="1e77e-139">Voer vervolgens de volgende opdracht uit om deze berichten vrij te geven aan alle oorspronkelijke ontvangers:</span><span class="sxs-lookup"><span data-stu-id="1e77e-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="1e77e-140">Nadat u een bericht hebt vrijgegeven, u het bericht niet meer vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="1e77e-140">After you release a message, you can't release it again.</span></span>
