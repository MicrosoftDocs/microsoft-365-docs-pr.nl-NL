---
title: Veelgestelde vragen over beveiliging tegen adresvervalsing
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen Veelgestelde vragen en antwoorden over anti-spoofing beveiliging weergeven in Exchange Online Protection (EOP).
ms.openlocfilehash: f567c7bc0c6a6efed7621cec86c5db4e616290b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616729"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="847a9-103">Veelgestelde vragen over beveiliging tegen adresvervalsing</span><span class="sxs-lookup"><span data-stu-id="847a9-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="847a9-104">Dit artikel bevat veelgestelde vragen en antwoorden over anti-spoofing beveiliging voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="847a9-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="847a9-105">Zie Veelgestelde vragen over [anti-spam beveiliging](anti-spam-protection-faq.md)voor vragen en antwoorden over bescherming tegen ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="847a9-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="847a9-106">Zie [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md) voor vragen en antwoorden over beveiliging tegen malware.</span><span class="sxs-lookup"><span data-stu-id="847a9-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="847a9-107">Waarom heeft Microsoft de inkomende e-mail ongeauthenticeerd laten voorkomen?</span><span class="sxs-lookup"><span data-stu-id="847a9-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="847a9-108">Microsoft heeft het voorbehoud dat het risico van het blijven van niet-geverifieerde binnenkomende e-mail hoger is dan het risico dat het verlies van geldige inkomende e-mail verloopt.</span><span class="sxs-lookup"><span data-stu-id="847a9-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="847a9-109">Zorgt inkomende e-mailberichten met ongeauthenticeerde inkomende e-mail ervoor dat legitiem e-mailbericht wordt gemarkeerd als spam?</span><span class="sxs-lookup"><span data-stu-id="847a9-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="847a9-110">Wanneer Microsoft deze functie inschakelt in 2018, zijn er enkele onbepaalde foutberichten opgetreden (goede berichten zijn gemarkeerd als beschadigd).</span><span class="sxs-lookup"><span data-stu-id="847a9-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="847a9-111">De afzenders zijn echter via de tijd aangepast aan de vereisten.</span><span class="sxs-lookup"><span data-stu-id="847a9-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="847a9-112">Het aantal berichten dat in de meeste gevallen als spoof werd gekenmerkt, is niet meer voor de meeste e-mail paden.</span><span class="sxs-lookup"><span data-stu-id="847a9-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="847a9-113">Microsoft zelf heeft de nieuwe verificatievereisten voor e-mailberichten eerst enkele weken goedgekeurd voordat u deze implementeert bij klanten.</span><span class="sxs-lookup"><span data-stu-id="847a9-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="847a9-114">Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.</span><span class="sxs-lookup"><span data-stu-id="847a9-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="847a9-115">Is spoof Intelligence beschikbaar voor klanten met Microsoft 365 zonder Defender for Office 365?</span><span class="sxs-lookup"><span data-stu-id="847a9-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="847a9-116">Ja.</span><span class="sxs-lookup"><span data-stu-id="847a9-116">Yes.</span></span> <span data-ttu-id="847a9-117">Vanaf oktober 2018 is spoof Intelligence beschikbaar voor alle organisaties met postvakken in Exchange Online, en zelfstandige EOP-organisaties zonder postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="847a9-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="847a9-118">Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?</span><span class="sxs-lookup"><span data-stu-id="847a9-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="847a9-119">Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="847a9-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="847a9-120">Ik ben een beheerder en ik weet niet alle bronnen voor berichten in mijn e-mail domein.</span><span class="sxs-lookup"><span data-stu-id="847a9-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="847a9-121">Zie [niet alle bronnen voor uw e-mail](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="847a9-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="847a9-122">Wat gebeurt er als ik anti-spoofing beveiliging voor mijn organisatie uitschakel?</span><span class="sxs-lookup"><span data-stu-id="847a9-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="847a9-123">U wordt aangeraden geen anti-spoofing beveiliging uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="847a9-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="847a9-124">Als u de beveiliging uitschakelt, kunnen er meer malafide en spamberichten in uw organisatie worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="847a9-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="847a9-125">Niet al phishing is niet altijd spoofing en niet alle vervalste berichten worden gemist.</span><span class="sxs-lookup"><span data-stu-id="847a9-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="847a9-126">Uw risico is echter groter.</span><span class="sxs-lookup"><span data-stu-id="847a9-126">However, your risk will be higher.</span></span>

<span data-ttu-id="847a9-127">Nu een [uitgebreide filtering voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, is het raadzaam om anti-spoofing-beveiliging niet langer uit te schakelen wanneer uw e-mail wordt doorgestuurd via een andere service vóór EOP.</span><span class="sxs-lookup"><span data-stu-id="847a9-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="847a9-128">Wordt in anti-spoofing bescherming bedoeld dat ik tegen phishing wordt beschermd?</span><span class="sxs-lookup"><span data-stu-id="847a9-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="847a9-129">Helaas, Nee, nee.</span><span class="sxs-lookup"><span data-stu-id="847a9-129">Unfortunately, no.</span></span> <span data-ttu-id="847a9-130">Hackers worden aangepast om andere technieken te gebruiken (bijvoorbeeld gemanipuleerd accounts of accounts in gratis e-mailservices).</span><span class="sxs-lookup"><span data-stu-id="847a9-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="847a9-131">De bescherming tegen phishing van deze andere typen veranderings methoden werkt echter sterk beter.</span><span class="sxs-lookup"><span data-stu-id="847a9-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="847a9-132">De beschermings lagen in EOP zijn geschikt voor samenwerking en samenwerken.</span><span class="sxs-lookup"><span data-stu-id="847a9-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="847a9-133">Andere grote e-mailservices blokkeren inkomende e-mail blokkeren?</span><span class="sxs-lookup"><span data-stu-id="847a9-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="847a9-134">Bijna alle grote e-mailservices voeren traditionele SPF-, DKIM-en DMARC-controles uit.</span><span class="sxs-lookup"><span data-stu-id="847a9-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="847a9-135">Voor sommige services zijn er nog meer strikte controles, maar enkele stappen voor het blokkeren van niet-geverifieerde e-mailberichten in EOP en behandelen ze als vervalste berichten.</span><span class="sxs-lookup"><span data-stu-id="847a9-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="847a9-136">De branche maakt echter meer kennis met betrekking tot problemen met niet-geverifieerde e-mail, met name vanwege het probleem van phishing.</span><span class="sxs-lookup"><span data-stu-id="847a9-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="847a9-137">Moet ik de beleidsinstelling voor geavanceerde spam van de instelling SPF-record (_MarkAsSpamSpfRecordHardFail_) nog steeds inschakelen als ik anti-spoofing inschakel?</span><span class="sxs-lookup"><span data-stu-id="847a9-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="847a9-138">Nee.</span><span class="sxs-lookup"><span data-stu-id="847a9-138">No.</span></span> <span data-ttu-id="847a9-139">Deze ASF-instelling is niet langer vereist.</span><span class="sxs-lookup"><span data-stu-id="847a9-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="847a9-140">De bescherming tegen spoofing beoordeelt standaard beide SPF-storing en een veel grotere set criteria.</span><span class="sxs-lookup"><span data-stu-id="847a9-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="847a9-141">Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.</span><span class="sxs-lookup"><span data-stu-id="847a9-141">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="847a9-142">We raden u aan deze functie uit te schakelen omdat dit bijna geen extra voordeel uitmaakt voor het detecteren van spam of phishing en daarom vooral foutberichten verloopt.</span><span class="sxs-lookup"><span data-stu-id="847a9-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="847a9-143">Zie voor meer informatie [Geavanceerde instellingen voor spam filter (ASF) in EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="847a9-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="847a9-144">Wordt in het schema voor het opnieuw schrijven van de afzender het doorgestuurde e-mail opgelost?</span><span class="sxs-lookup"><span data-stu-id="847a9-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="847a9-145">SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op.</span><span class="sxs-lookup"><span data-stu-id="847a9-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="847a9-146">Wanneer u de SMTP **-e-mail** herschrijft van, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF op de volgende bestemming doorgeeft.</span><span class="sxs-lookup"><span data-stu-id="847a9-146">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="847a9-147">Aangezien ook anti-spoofing is gebaseerd op het **van** -adres in combinatie met de **e-mail van** of het dkim-handtekeningen domein (of andere signalen), is het niet voldoende om te voorkomen dat doorgestuurde e-mailberichten worden gemarkeerd als spoofed.</span><span class="sxs-lookup"><span data-stu-id="847a9-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
