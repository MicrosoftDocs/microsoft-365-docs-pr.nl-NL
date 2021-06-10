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
description: Meer informatie over de standaardinstelling voor beveiliging in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f197556426171b867b49781b38ea5f5116f80aa2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861525"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="d7692-103">Standaard beveiligd in Office 365</span><span class="sxs-lookup"><span data-stu-id="d7692-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d7692-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d7692-104">**Applies to**</span></span>
- [<span data-ttu-id="d7692-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d7692-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d7692-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d7692-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d7692-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7692-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d7692-108">'Standaard beveiligd' is een term die wordt gebruikt om de standaardinstellingen te definiëren die zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d7692-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="d7692-109">Beveiliging moet echter in balans zijn met productiviteit.</span><span class="sxs-lookup"><span data-stu-id="d7692-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="d7692-110">Dit kan onder andere het uitbalanceren van de volgende gegevens omvatten:</span><span class="sxs-lookup"><span data-stu-id="d7692-110">This can include balancing across:</span></span>

- <span data-ttu-id="d7692-111">**Bruikbaarheid:** Instellingen mag de productiviteit van gebruikers niet in de weg staan.</span><span class="sxs-lookup"><span data-stu-id="d7692-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="d7692-112">**Risico:** Beveiliging kan belangrijke activiteiten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="d7692-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="d7692-113">**Oudere instellingen:** Sommige configuraties voor oudere producten en functies moeten mogelijk worden onderhouden om zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.</span><span class="sxs-lookup"><span data-stu-id="d7692-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="d7692-114">Microsoft 365 organisaties met postvakken in Exchange Online worden beveiligd door Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d7692-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d7692-115">Deze beveiliging omvat:</span><span class="sxs-lookup"><span data-stu-id="d7692-115">This protection includes:</span></span>

- <span data-ttu-id="d7692-116">E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden worden op de hoogte gesteld.</span><span class="sxs-lookup"><span data-stu-id="d7692-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="d7692-117">Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7692-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="d7692-118">E-mail die is geïdentificeerd als phishing met veel vertrouwen, wordt verwerkt volgens de antispambeleidsactie.</span><span class="sxs-lookup"><span data-stu-id="d7692-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="d7692-119">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7692-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d7692-120">Zie voor meer informatie over EOP [Exchange Online Protection overzicht.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d7692-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="d7692-121">Omdat Microsoft onze klanten standaard veilig wil houden, worden sommige tenants niet toegepast op malware of phishing met veel vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="d7692-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="d7692-122">Deze overschrijven zijn:</span><span class="sxs-lookup"><span data-stu-id="d7692-122">These overrides include:</span></span>

- <span data-ttu-id="d7692-123">Lijsten met toegestane afzenders of toegestane domeinlijsten (antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="d7692-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="d7692-124">Outlook Safe afzenders</span><span class="sxs-lookup"><span data-stu-id="d7692-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="d7692-125">Ip Allow List (verbindingsfiltering)</span><span class="sxs-lookup"><span data-stu-id="d7692-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="d7692-126">Meer informatie over deze overschrijven vindt u in Lijsten met veilige [afzenders maken.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d7692-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7692-127">We hebben de actie  Bericht verplaatsen naar map Ongewenste e-mail afgeschaft voor een uitspraak over phishing-e-mail met veel vertrouwen in het antispambeleid van EOP. </span><span class="sxs-lookup"><span data-stu-id="d7692-127">We have deprecated the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="d7692-128">Antispambeleid dat deze actie gebruikt voor phishingberichten met veel vertrouwen, wordt geconverteerd naar **quarantainebericht.**</span><span class="sxs-lookup"><span data-stu-id="d7692-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="d7692-129">De **actie Bericht omleiden naar e-mailadres** voor phishingberichten met veel vertrouwen wordt niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="d7692-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="d7692-130">Beveiliging is standaard geen instelling die kan worden in- of uitgeschakeld, maar is de manier waarop onze filtering werkt uit het vak om potentieel gevaarlijke of ongewenste berichten uit uw postvakken te houden.</span><span class="sxs-lookup"><span data-stu-id="d7692-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="d7692-131">Malware en phishingberichten met veel vertrouwen moeten in quarantaine worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="d7692-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="d7692-132">Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware of phishing met veel vertrouwen, en ze kunnen ook van hier naar Microsoft onwaar positieven rapporteren.</span><span class="sxs-lookup"><span data-stu-id="d7692-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="d7692-133">Zie Berichten en bestanden in quarantaine beheren als [beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d7692-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="d7692-134">Meer informatie over waarom we dit doen</span><span class="sxs-lookup"><span data-stu-id="d7692-134">More on why we're doing this</span></span>

<span data-ttu-id="d7692-135">De standaardinstelling van beveiliging is: we ondernemen dezelfde actie voor het bericht dat u zou ondernemen als u wist dat het bericht schadelijk was, zelfs wanneer een geconfigureerde uitzondering anders zou toestaan dat het bericht wordt bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d7692-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="d7692-136">Dit is dezelfde methode die we altijd hebben gebruikt voor malware en nu breiden we ditzelfde gedrag uit tot phishingberichten met veel vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="d7692-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="d7692-137">Onze gegevens geven aan dat een gebruiker 30 keer meer kans heeft op een schadelijke koppeling in berichten in de map Ongewenste e-mail versus Quarantaine.</span><span class="sxs-lookup"><span data-stu-id="d7692-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="d7692-138">Onze gegevens geven ook aan dat de fout-positieve rente (goede berichten die als slecht zijn gemarkeerd) voor phishingberichten met hoog vertrouwen zeer laag is en dat beheerders eventuele fout-positieven kunnen oplossen met beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="d7692-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="d7692-139">We hebben ook vastgesteld dat de toegestane afzender en toegestane domeinlijsten in antispambeleid en Safe Senders in Outlook te breed waren en meer schade dan goed veroorzaakten.</span><span class="sxs-lookup"><span data-stu-id="d7692-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="d7692-140">Anders gezegd: als beveiligingsservice handelen we namens u om te voorkomen dat uw gebruikers worden gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="d7692-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="d7692-141">Uitzonderingen</span><span class="sxs-lookup"><span data-stu-id="d7692-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="d7692-142">In juli 2021 wordt beveiliging standaard uitgebreid tot Exchange regels voor e-mailstroom (ook wel transportregels genoemd).</span><span class="sxs-lookup"><span data-stu-id="d7692-142">In July 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d7692-143">Als u e-mailstroomregels gebruikt om phishingsimulaties van derden of ongefilterde bezorging toe te staan [](configure-advanced-delivery.md) aan postvakken voor beveiligingsbewerkingen, moet u deze regels uiteindelijk verwijderen en overschakelen naar het geavanceerde bezorgingsbeleid wanneer de functie voor u _beschikbaar is._</span><span class="sxs-lookup"><span data-stu-id="d7692-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="d7692-144">De enige overschrijven die phishing met veel vertrouwen toestaat om filteren te omzeilen, zijn regels voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="d7692-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="d7692-145">Zie E-mailstroomregels gebruiken om de SCL in berichten in te stellen als u regels voor e-mailstroom wilt gebruiken om filteren [te omzeilen.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="d7692-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="d7692-146">U moet in de volgende scenario's alleen overschrijven gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d7692-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="d7692-147">Phishingsimulaties: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d7692-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="d7692-148">Beveiligings-/SecOps-postvakken: speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="d7692-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="d7692-149">Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="d7692-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="d7692-150">Filters van derden: Secure is standaard niet van toepassing wanneer de MX-record van het domein niet naar de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7692-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="d7692-151">Onwaar-positieven: Mogelijk wilt u bepaalde berichten die nog steeds door Microsoft worden geanalyseerd, tijdelijk toestaan [via beheerdersinzendingen.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d7692-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="d7692-152">Net als bij alle overschrijvingen wordt aanbevolen dat deze tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d7692-152">As with all overrides, it is recommended that they are temporary.</span></span>
