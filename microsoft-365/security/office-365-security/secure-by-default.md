---
title: Standaard beveiligd in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over de standaardbeveiligingsinstelling in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288511"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="34255-103">Standaard beveiligd in Office 365</span><span class="sxs-lookup"><span data-stu-id="34255-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34255-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="34255-104">**Applies to**</span></span>
- [<span data-ttu-id="34255-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="34255-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34255-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="34255-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="34255-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34255-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="34255-108">Standaard beveiligd is een term die wordt gebruikt om de standaardinstellingen te definiëren die zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="34255-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="34255-109">Beveiliging moet echter in balans zijn met productiviteit.</span><span class="sxs-lookup"><span data-stu-id="34255-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="34255-110">Dit kan onder andere zijn:</span><span class="sxs-lookup"><span data-stu-id="34255-110">This can include balancing across:</span></span>

- <span data-ttu-id="34255-111">**Bruikbaarheid:** instellingen mogen de productiviteit van gebruikers niet in de weg staan.</span><span class="sxs-lookup"><span data-stu-id="34255-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="34255-112">**Risico:** beveiliging kan belangrijke activiteiten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="34255-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="34255-113">**Oudere instellingen:** sommige configuraties voor oudere producten en functies moeten mogelijk vanwege zakelijke redenen worden bewaard, zelfs als nieuwe, moderne instellingen zijn verbeterd.</span><span class="sxs-lookup"><span data-stu-id="34255-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="34255-114">Microsoft 365-organisaties met postvakken in Exchange Online worden beveiligd door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="34255-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="34255-115">Deze beveiliging omvat:</span><span class="sxs-lookup"><span data-stu-id="34255-115">This protection includes:</span></span>

- <span data-ttu-id="34255-116">E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden worden op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="34255-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="34255-117">Zie [Antimalwarebeleid configureren in EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="34255-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="34255-118">E-mailberichten die zijn aangemerkt als zeer vertrouwelijk phishing, worden verwerkt volgens de actie in het antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="34255-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="34255-119">Zie [Antispambeleid configureren in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="34255-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="34255-120">Zie het overzicht van [Exchange Online Protection](exchange-online-protection-overview.md)voor meer informatie over EOP.</span><span class="sxs-lookup"><span data-stu-id="34255-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="34255-121">Omdat Microsoft onze klanten standaard beveiligd wil houden, worden sommige tenants niet toegepast op malware of phishing met hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="34255-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="34255-122">Dit zijn onder andere de volgende overschrijvingen:</span><span class="sxs-lookup"><span data-stu-id="34255-122">These overrides include:</span></span>

- <span data-ttu-id="34255-123">Lijsten met toegestane afzenders of lijsten met toegestane domeinen (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="34255-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="34255-124">Veilige afzenders in Outlook</span><span class="sxs-lookup"><span data-stu-id="34255-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="34255-125">Lijst met toegestane IP-adressen (filteren van verbinding)</span><span class="sxs-lookup"><span data-stu-id="34255-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="34255-126">Meer informatie over deze overschrijvingen vindt u in [Lijsten met veilige afzenders maken.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="34255-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34255-127">We zijn bezig de actie Bericht  verplaatsen naar map Ongewenste e-mail uit te stellen, omdat we in EOP antispambeleid e-mails met hoge vertrouwens-phishing-e-mails kunnen aanmaken. </span><span class="sxs-lookup"><span data-stu-id="34255-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="34255-128">Antispambeleid dat deze actie gebruikt om zeer vertrouwelijk phishing-berichten te gebruiken, wordt geconverteerd naar **quarantainebericht.**</span><span class="sxs-lookup"><span data-stu-id="34255-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="34255-129">De **actie Bericht omleiden naar e-mailadres** voor zeer goede phishingberichten wordt niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="34255-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="34255-130">Standaard beveiligen is geen instelling die kan worden in- of uitgeschakeld, maar is de manier waarop wordt gefilterd om mogelijk gevaarlijke of ongewenste berichten uit uw postvakken te houden.</span><span class="sxs-lookup"><span data-stu-id="34255-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="34255-131">Malware en phishingberichten met hoge betrouwbaarheid moeten in quarantaine worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="34255-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="34255-132">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware of phishing met een hoge betrouwbaarheid en kunnen van hier naar Microsoft ook fout-positieven rapporteren.</span><span class="sxs-lookup"><span data-stu-id="34255-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="34255-133">Zie Berichten en bestanden in quarantaine beheren [als beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="34255-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="34255-134">Meer informatie over waarom we dit doen</span><span class="sxs-lookup"><span data-stu-id="34255-134">More on why we're doing this</span></span>

<span data-ttu-id="34255-135">De gedachte om standaard veilig te zijn is: we voeren dezelfde actie uit op het bericht dat u zou ondernemen als u de schadelijke berichten kent, zelfs wanneer een geconfigureerde uitzondering het bericht anders zou bezorgen.</span><span class="sxs-lookup"><span data-stu-id="34255-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="34255-136">Dit is dezelfde methode die we altijd al hebben gebruikt voor malware, en nu wordt ditzelfde gedrag uitgebreid naar phishingberichten met een hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="34255-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="34255-137">Uit onze gegevens blijkt dat een gebruiker 30 keer vaker op een schadelijke koppeling in berichten in de map Ongewenste e-mail en op Quarantaine klikt.</span><span class="sxs-lookup"><span data-stu-id="34255-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="34255-138">Uit onze gegevens blijkt ook dat de fout-positieve snelheid (goede berichten gemarkeerd als slecht) voor phishingberichten met hoge betrouwbaarheid zeer laag is en dat beheerders eventuele fout-positieven kunnen oplossen met beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="34255-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="34255-139">We hebben ook vastgesteld dat de toegestane afzender en toegestane domeinlijsten in antispambeleid en veilige afzenders in Outlook te ruim waren en voor meer schade dan goed waren.</span><span class="sxs-lookup"><span data-stu-id="34255-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="34255-140">Om dit op een andere manier te doen: als beveiligingsservice handelen we namens u om te voorkomen dat uw gebruikers worden gehackt.</span><span class="sxs-lookup"><span data-stu-id="34255-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="34255-141">Uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="34255-141">Exceptions</span></span>

<span data-ttu-id="34255-142">Alleen Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd) zijn de enige overschakeling die een zeer betrouwbaarheids-phishingbericht toestaat om filters te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="34255-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="34255-143">Zie Regels voor de e-mailstroom gebruiken om de SCL in berichten in te stellen als u regels voor de [e-mailstroom wilt gebruiken](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)om filters te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="34255-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="34255-144">U kunt overschrijven het beste in de volgende scenario's gebruiken:</span><span class="sxs-lookup"><span data-stu-id="34255-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="34255-145">Phishing-phishing-phishing-aanvallen: Gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="34255-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="34255-146">Beveiligings-/SecOps-postvakken: toegewezen postvakken die door beveiligingsteams worden gebruikt om niet-gefilterde berichten te krijgen (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="34255-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="34255-147">Teams kunnen vervolgens controleren of ze schadelijke inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="34255-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="34255-148">Filters van derden: Standaard is Secure niet van toepassing wanneer de MX-record van het domein niet naar Office 365 betekent.</span><span class="sxs-lookup"><span data-stu-id="34255-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="34255-149">Fout-positieven: U wilt mogelijk tijdelijk toestaan dat bepaalde berichten die nog door Microsoft worden geanalyseerd [via beheerdersinzendingen, worden verzonden.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="34255-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="34255-150">Net als bij alle overschrijven, wordt het aanbevolen dat deze tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="34255-150">As with all overrides, it is recommended that they are temporary.</span></span>
