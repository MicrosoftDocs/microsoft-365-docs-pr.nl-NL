---
title: Veelgestelde vragen over quarantaine
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
description: Antwoorden op veelgestelde vragen over quarantaine in Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634422"
---
# <a name="quarantine-faq"></a><span data-ttu-id="6045f-103">Veelgestelde vragen over quarantaine</span><span class="sxs-lookup"><span data-stu-id="6045f-103">Quarantine FAQ</span></span>

<span data-ttu-id="6045f-104">In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over quarantaine voor Microsoft 365-klanten met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="6045f-104">This topic provides frequently asked questions and answers about quarantine for Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="6045f-105">V: Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?</span><span class="sxs-lookup"><span data-stu-id="6045f-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="6045f-106">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware.</span><span class="sxs-lookup"><span data-stu-id="6045f-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="6045f-107">Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="6045f-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="6045f-108">V: Hoe quarantaine spam?</span><span class="sxs-lookup"><span data-stu-id="6045f-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="6045f-109">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-109">A.</span></span> <span data-ttu-id="6045f-110">Berichten die door spamfilter worden geclassificeerd als spam of bulk-e-mail worden standaard naar het postvak van de gebruiker verzonden en worden verplaatst naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="6045f-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="6045f-111">Maar u in plaats daarvan antispambeleid maken en configureren om spam of bulke-mailberichten in quarantaine te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="6045f-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="6045f-112">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6045f-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="6045f-113">V: Hoe geef ik gebruikers toegang tot de quarantaine?</span><span class="sxs-lookup"><span data-stu-id="6045f-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="6045f-114">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-114">A.</span></span> <span data-ttu-id="6045f-115">Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn eigen berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="6045f-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="6045f-116">Standalone EOP vereist dat gebruikers worden vertegenwoordigd als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie).</span><span class="sxs-lookup"><span data-stu-id="6045f-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="6045f-117">Zie [E-mailgebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="6045f-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="6045f-118">V: Welke berichten kunnen eindgebruikers in quarantaine openen?</span><span class="sxs-lookup"><span data-stu-id="6045f-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="6045f-119">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-119">A.</span></span> <span data-ttu-id="6045f-120">Gebruikers hebben toegang tot spam, bulke-mail en (vanaf april 2020) phishingberichten waar ze een ontvanger zijn.</span><span class="sxs-lookup"><span data-stu-id="6045f-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="6045f-121">Eindgebruikers hebben geen toegang tot in quarantaine geplaatste malware, phishing met een hoog vertrouwen of berichten die in quarantaine zijn geplaatst vanwege de **actie Het bericht leveren aan de gehoste quarantaineactie** in de regels voor e-mailstromen (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="6045f-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="6045f-122">Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over gebruikers die toegang hebben tot in quarantaine geplaatste berichten.</span><span class="sxs-lookup"><span data-stu-id="6045f-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="6045f-123">V: Hoe lang worden berichten in quarantaine gehouden?</span><span class="sxs-lookup"><span data-stu-id="6045f-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="6045f-124">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-124">A.</span></span> <span data-ttu-id="6045f-125">U configureert hoe lang spam- en phishing- en bulke-mailberichten in quarantaine worden gehouden met behulp van antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="6045f-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="6045f-126">De standaard instelling is 30 dagen, wat ook het maximum is.</span><span class="sxs-lookup"><span data-stu-id="6045f-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="6045f-127">Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="6045f-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="6045f-128">Voor berichten die in quarantaine zijn geplaatst door de regelactie E-mailstroom **Breng het bericht naar de gehoste quarantaine,** worden de berichten 30 dagen in quarantaine gehouden.</span><span class="sxs-lookup"><span data-stu-id="6045f-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="6045f-129">U deze duur niet configureren.</span><span class="sxs-lookup"><span data-stu-id="6045f-129">You can't configure this duration.</span></span>

<span data-ttu-id="6045f-130">Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="6045f-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="6045f-131">V: Kan ik meer dan één in quarantaine geplaatst bericht tegelijk vrijgeven of rapporteren?</span><span class="sxs-lookup"><span data-stu-id="6045f-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="6045f-132">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-132">A.</span></span> <span data-ttu-id="6045f-133">In het Security & Compliance Center u maximaal 100 berichten tegelijk selecteren en vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="6045f-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="6045f-134">Beheerders kunnen de cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) en [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) gebruiken in Exchange Online PowerShell of standalone Exchange Online Protection PowerShell om in bulk in quarantaine geplaatste berichten te vinden en vrij te geven en valse positieven in bulk te melden.</span><span class="sxs-lookup"><span data-stu-id="6045f-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="6045f-135">V: Worden wildcards ondersteund bij het zoeken naar in quarantaine geplaatste berichten?</span><span class="sxs-lookup"><span data-stu-id="6045f-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="6045f-136">Kan ik zoeken naar in quarantaine geplaatste berichten voor een specifiek domein?</span><span class="sxs-lookup"><span data-stu-id="6045f-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="6045f-137">A.</span><span class="sxs-lookup"><span data-stu-id="6045f-137">A.</span></span> <span data-ttu-id="6045f-138">Jokertekens worden niet ondersteund in het Beveiligingscentrum & Compliance.</span><span class="sxs-lookup"><span data-stu-id="6045f-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="6045f-139">Wanneer u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven.</span><span class="sxs-lookup"><span data-stu-id="6045f-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="6045f-140">U echter wildcards gebruiken in Exchange Online PowerShell of Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6045f-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="6045f-141">Voer bijvoorbeeld de volgende opdracht uit om spamin quarantaine geplaatste berichten van alle afzenders in het domein contoso.com te vinden:</span><span class="sxs-lookup"><span data-stu-id="6045f-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="6045f-142">Voer vervolgens de volgende opdracht uit om deze berichten vrij te geven aan alle oorspronkelijke ontvangers:</span><span class="sxs-lookup"><span data-stu-id="6045f-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="6045f-143">Nadat u een bericht hebt vrijgegeven, u het bericht niet meer vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="6045f-143">After you release a message, you can't release it again.</span></span>
