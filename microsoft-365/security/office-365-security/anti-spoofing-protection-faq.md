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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen veelgestelde vragen en antwoorden over bescherming tegen spoofing bekijken in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288907"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="74fab-103">Veelgestelde vragen over beveiliging tegen adresvervalsing</span><span class="sxs-lookup"><span data-stu-id="74fab-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74fab-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="74fab-104">**Applies to**</span></span>
- [<span data-ttu-id="74fab-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="74fab-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="74fab-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="74fab-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="74fab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74fab-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="74fab-108">Dit artikel bevat veelgestelde vragen en antwoorden over bescherming tegen spoofing voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="74fab-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="74fab-109">Zie Veelgestelde vragen en antwoorden over bescherming tegen ongewenste [e-mail.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="74fab-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="74fab-110">Voor vragen en antwoorden over bescherming tegen malware, zie [veelgestelde vragen over bescherming tegen malware](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="74fab-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="74fab-111">Waarom heeft Microsoft gekozen voor ongewenste inkomende e-mail?</span><span class="sxs-lookup"><span data-stu-id="74fab-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="74fab-112">Microsoft is van mening dat het risico op het blijven toestaan van niet-geauteerde inkomende e-mail hoger is dan het risico op het verliezen van legitieme inkomende e-mail.</span><span class="sxs-lookup"><span data-stu-id="74fab-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="74fab-113">Zorgt niet-geauteerde inkomende e-mail ervoor dat legitieme e-mail wordt gemarkeerd als spam?</span><span class="sxs-lookup"><span data-stu-id="74fab-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="74fab-114">Toen Microsoft deze functie in 2018 inschakelen, gebeurde er een aantal fout-positieven (goede berichten waren gemarkeerd als slecht).</span><span class="sxs-lookup"><span data-stu-id="74fab-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="74fab-115">Na een aantal keer hebben afzenders zich echter aan de vereisten aangepast.</span><span class="sxs-lookup"><span data-stu-id="74fab-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="74fab-116">Het aantal berichten dat onjuist is geïdentificeerd als vervalst, werd steeds belangrijker voor de meeste e-mailpaden.</span><span class="sxs-lookup"><span data-stu-id="74fab-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="74fab-117">Microsoft zelf heeft enkele weken voor de implementatie bij klanten de nieuwe vereisten voor e-mailverificatie in gebruik genomen.</span><span class="sxs-lookup"><span data-stu-id="74fab-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="74fab-118">Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.</span><span class="sxs-lookup"><span data-stu-id="74fab-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="74fab-119">Is spoof intelligence beschikbaar voor Microsoft 365-klanten zonder Defender voor Office 365?</span><span class="sxs-lookup"><span data-stu-id="74fab-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="74fab-120">Ja.</span><span class="sxs-lookup"><span data-stu-id="74fab-120">Yes.</span></span> <span data-ttu-id="74fab-121">Vanaf oktober 2018 is spoof intelligence beschikbaar voor alle organisaties met postvakken in Exchange Online en zelfstandige EOP-organisaties zonder Exchange Online-postvakken.</span><span class="sxs-lookup"><span data-stu-id="74fab-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="74fab-122">Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?</span><span class="sxs-lookup"><span data-stu-id="74fab-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="74fab-123">Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="74fab-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="74fab-124">Ik ben een beheerder en ik weet niet alle bronnen voor berichten in mijn e-maildomein.</span><span class="sxs-lookup"><span data-stu-id="74fab-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="74fab-125">Zie [U weet niet alle bronnen voor uw e-mail.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="74fab-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="74fab-126">Wat gebeurt er als ik de beveiliging tegen spoofing voor mijn organisatie uitspoe?</span><span class="sxs-lookup"><span data-stu-id="74fab-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="74fab-127">Het wordt afgeraden om bescherming tegen spoofing uit te uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="74fab-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="74fab-128">Door de beveiliging uit te stellen, kunnen er meer phishing- en spamberichten worden afgeleverd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="74fab-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="74fab-129">Niet alle phishingberichten worden vervalst en niet alle vervalste berichten worden gemist.</span><span class="sxs-lookup"><span data-stu-id="74fab-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="74fab-130">Uw risico is echter hoger.</span><span class="sxs-lookup"><span data-stu-id="74fab-130">However, your risk will be higher.</span></span>

<span data-ttu-id="74fab-131">Nu [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, raden we niet langer aan om de beveiliging tegen spoofing uit te schakelen wanneer uw e-mail wordt doorverrouteerd via een andere service vóór EOP.</span><span class="sxs-lookup"><span data-stu-id="74fab-131">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="74fab-132">Betekent de beveiliging tegen spoofing dat ik tegen alle phishing ben beveiligd?</span><span class="sxs-lookup"><span data-stu-id="74fab-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="74fab-133">Helaas niet.</span><span class="sxs-lookup"><span data-stu-id="74fab-133">Unfortunately, no.</span></span> <span data-ttu-id="74fab-134">Aanvallers passen zich aan om andere technieken te gebruiken (bijvoorbeeld gekromde accounts of accounts in gratis e-mailservices).</span><span class="sxs-lookup"><span data-stu-id="74fab-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="74fab-135">Anti-phishingbeveiliging werkt echter veel beter om deze andere typen phishingmethoden te detecteren.</span><span class="sxs-lookup"><span data-stu-id="74fab-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="74fab-136">De beveiligingslagen in EOP zijn ontworpen om samen te werken en elkaar te beschermen.</span><span class="sxs-lookup"><span data-stu-id="74fab-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="74fab-137">Blokkeren andere grote e-mailservices niet-geauteerde inkomende e-mail?</span><span class="sxs-lookup"><span data-stu-id="74fab-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="74fab-138">Bijna alle grote e-mailservices implementeren traditionele SPF-, DKIM- en DMARC-controles.</span><span class="sxs-lookup"><span data-stu-id="74fab-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="74fab-139">Sommige services hebben andere, striktere controles, maar slechts weinig services zijn zo ver als EOP om niet-geauteerde e-mail te blokkeren en deze te behandelen als vervalste berichten.</span><span class="sxs-lookup"><span data-stu-id="74fab-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="74fab-140">De branche wordt echter steeds meer op de hoogte van problemen met niet-geauteerde e-mail, met name vanwege het probleem van phishing.</span><span class="sxs-lookup"><span data-stu-id="74fab-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="74fab-141">Moet ik nog steeds de instelling voor het geavanceerde spamfilter 'SPF-record: hard fail'_(MarkAsSpamSpfRecordHardFail)_ inschakelen als ik anti-spoofing inschakelen?</span><span class="sxs-lookup"><span data-stu-id="74fab-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="74fab-142">Nee.</span><span class="sxs-lookup"><span data-stu-id="74fab-142">No.</span></span> <span data-ttu-id="74fab-143">Deze ASF-instelling is niet meer vereist.</span><span class="sxs-lookup"><span data-stu-id="74fab-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="74fab-144">Beveiliging tegen adresvervalsing houdt in dat zowel SPF hard mislukt als dat er meer criteria worden gehanteerd.</span><span class="sxs-lookup"><span data-stu-id="74fab-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="74fab-145">Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.</span><span class="sxs-lookup"><span data-stu-id="74fab-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="74fab-146">U wordt aangeraden deze functie uit te schakelen, omdat het vrijwel geen extra voordeel biedt voor het detecteren van spam of phishingbericht, en in plaats daarvan voornamelijk fout-positieven genereert.</span><span class="sxs-lookup"><span data-stu-id="74fab-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="74fab-147">Zie [asf-instellingen (Advanced Spam Filter) in EOP](advanced-spam-filtering-asf-options.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="74fab-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="74fab-148">Helpt het schema Voor het herschrijven van afzenders om doorgestuurde e-mail op te lossen?</span><span class="sxs-lookup"><span data-stu-id="74fab-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="74fab-149">SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op.</span><span class="sxs-lookup"><span data-stu-id="74fab-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="74fab-150">Door SMTP **MAIL FROM** te herschrijven, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF passeert op de volgende bestemming.</span><span class="sxs-lookup"><span data-stu-id="74fab-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="74fab-151">Omdat antivervalsing echter is gebaseerd op het **Van-adres** in combinatie met het domein voor **MAIL FROM-** of DKIM-ondertekening (of andere signalen), is het niet voldoende om te voorkomen dat door SRS doorgestuurde e-mail wordt gemarkeerd als vervalst.</span><span class="sxs-lookup"><span data-stu-id="74fab-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
