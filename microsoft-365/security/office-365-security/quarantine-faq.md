---
title: Veelgestelde vragen over quarantaine berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
description: Beheerders kunnen Veelgestelde vragen en antwoorden over berichten in quarantaine weergeven in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00768b3584c854ef0648f75f1966a8fa331b2866
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413422"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="ce878-103">Veelgestelde vragen over quarantaine berichten</span><span class="sxs-lookup"><span data-stu-id="ce878-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ce878-104">In dit onderwerp vindt u veelgestelde vragen en antwoorden over geposte e-mailberichten voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="ce878-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="ce878-105">Zie Veelgestelde vragen over [anti-spam beveiliging](anti-spam-protection-faq.md)voor vragen en antwoorden over bescherming tegen ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="ce878-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="ce878-106">Zie [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)voor vragen en antwoorden over beveiliging tegen malware.</span><span class="sxs-lookup"><span data-stu-id="ce878-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="ce878-107">Zie [Veelgestelde vragen over beveiliging tegen spoofing](anti-spoofing-protection-faq.md)voor vragen en antwoorden over beveiliging tegen spoofing.</span><span class="sxs-lookup"><span data-stu-id="ce878-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="ce878-108">Hoe beheer ik berichten die zijn gequarantined voor malware?</span><span class="sxs-lookup"><span data-stu-id="ce878-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="ce878-109">Alleen beheerders kunnen berichten beheren die zijn gequarantined voor malware.</span><span class="sxs-lookup"><span data-stu-id="ce878-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="ce878-110">Zie voor meer informatie [gequarantinee berichten en bestanden beheren als beheerder](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ce878-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="ce878-111">Hoe kan ik spam in quarantaine plaatsen?</span><span class="sxs-lookup"><span data-stu-id="ce878-111">How do I quarantine spam?</span></span>

<span data-ttu-id="ce878-112">Standaard worden berichten die als ongewenste e-mail of bulksgewijs e-mailbericht zijn geclassificeerd via spamfilters bezorgd in het postvak van de gebruiker en worden ze naar de map Ongewenste E-mail verplaatst.</span><span class="sxs-lookup"><span data-stu-id="ce878-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="ce878-113">U kunt echter wel antispam-beleidsregels maken en configureren zodat u in plaats daarvan spam en bulk-e-mailberichten kunt maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="ce878-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="ce878-114">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce878-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="ce878-115">Hoe kan ik gebruikers toegang geven tot de quarantaine?</span><span class="sxs-lookup"><span data-stu-id="ce878-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="ce878-116">Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn of haar eigen berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="ce878-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="ce878-117">Voor zelfstandige EOP moet gebruikers worden weergegeven als e-mail gebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie).</span><span class="sxs-lookup"><span data-stu-id="ce878-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="ce878-118">Zie [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.</span><span class="sxs-lookup"><span data-stu-id="ce878-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="ce878-119">Met welke berichten hebben gebruikers toegang tot de eindgebruikers in quarantaine?</span><span class="sxs-lookup"><span data-stu-id="ce878-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="ce878-120">Gebruikers hebben toegang tot spam, bulk-e-mail en (vanaf april 2020) malafide berichten waarin ze een geadresseerde zijn.</span><span class="sxs-lookup"><span data-stu-id="ce878-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="ce878-121">Eindgebruikers hebben geen toegang tot geïsoleerde malware van de werkstroom of berichten die zijn gequarantined vanwege het **bezorgen van het bericht naar de actie in de gehoste quarantaine** -actie in de e-mail stroom regels (ook wel de zogenaamde transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="ce878-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ce878-122">Zie geplaatste [berichten in quarantaine plaatsen en vrijgeven als een gebruiker](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over gebruikers die quarantaine berichten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce878-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="ce878-123">Hoe lang worden berichten in de quarantaine bewaard?</span><span class="sxs-lookup"><span data-stu-id="ce878-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="ce878-124">U configureert hoe lang spamberichten, phishing en bulk-e-mailberichten in quarantaine worden bewaard met behulp van antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="ce878-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="ce878-125">De standaardinstelling is 30 dagen, wat ook het maximum is.</span><span class="sxs-lookup"><span data-stu-id="ce878-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="ce878-126">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce878-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="ce878-127">Voor berichten waarvan de actie de e-mail stroom regel is gequarantined, wordt **het bericht verzonden naar de gehoste quarantaine**, en worden de berichten in quarantaine bewaard gedurende 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="ce878-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="ce878-128">U kunt deze duur niet configureren.</span><span class="sxs-lookup"><span data-stu-id="ce878-128">You can't configure this duration.</span></span>

<span data-ttu-id="ce878-129">Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="ce878-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="ce878-130">Kan ik meerdere berichten in quarantaine plaatsen of rapporteren?</span><span class="sxs-lookup"><span data-stu-id="ce878-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="ce878-131">In het beveiligings & nalevings centrum kunt u 100-berichten tegelijk selecteren en vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="ce878-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="ce878-132">Beheerders kunnen gebruikmaken van de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) en [release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell of zelfstandige EOP PowerShell om geplaatste berichten bulksgewijs te zoeken en uit te brengen, en om fout-positieven in bulk te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="ce878-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="ce878-133">Worden jokertekens ondersteund bij het zoeken naar berichten in quarantaine?</span><span class="sxs-lookup"><span data-stu-id="ce878-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="ce878-134">Kan ik zoeken naar berichten in quarantaine voor een bepaald domein?</span><span class="sxs-lookup"><span data-stu-id="ce878-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="ce878-135">Jokertekens worden niet ondersteund in het beveiligings & nalevings centrum.</span><span class="sxs-lookup"><span data-stu-id="ce878-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="ce878-136">Als u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven.</span><span class="sxs-lookup"><span data-stu-id="ce878-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="ce878-137">U kunt jokertekens gebruiken in Exchange Online PowerShell of zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce878-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="ce878-138">Voer bijvoorbeeld de volgende opdracht uit om spamberichten in quarantaine te plaatsen van alle afzenders in de domein contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ce878-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="ce878-139">Voer vervolgens de volgende opdracht uit om die berichten op alle oorspronkelijke geadresseerden te brengen:</span><span class="sxs-lookup"><span data-stu-id="ce878-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="ce878-140">Wanneer u een bericht hebt vrijgegeven, kunt u het niet meer vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="ce878-140">After you release a message, you can't release it again.</span></span>
