---
title: Uitgaande bezorgingspools
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lees hoe de bezorgingsgroepen worden gebruikt om de reputatie van e-mailservers in de Microsoft 365 beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137716"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="5ced3-103">Uitgaande bezorgingspools</span><span class="sxs-lookup"><span data-stu-id="5ced3-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ced3-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="5ced3-104">**Applies to**</span></span>
- [<span data-ttu-id="5ced3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ced3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ced3-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="5ced3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ced3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ced3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ced3-108">E-mailservers in Microsoft 365 datacenters zijn mogelijk tijdelijk schuldig aan het verzenden van spam.</span><span class="sxs-lookup"><span data-stu-id="5ced3-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="5ced3-109">Bijvoorbeeld een malware- of schadelijke spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of gecompromitteerde Microsoft 365 accounts.</span><span class="sxs-lookup"><span data-stu-id="5ced3-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="5ced3-110">Aanvallers proberen detectie ook te voorkomen door berichten door te sturen via Microsoft 365 doorsturen.</span><span class="sxs-lookup"><span data-stu-id="5ced3-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="5ced3-111">Deze scenario's kunnen resulteren in het IP-adres van de Microsoft 365 datacenterservers die worden weergegeven op blokkeringen van derden.</span><span class="sxs-lookup"><span data-stu-id="5ced3-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="5ced3-112">Doel-e-mailorganisaties die deze blokkeringen gebruiken, weigeren e-mail uit deze berichtenbronnen.</span><span class="sxs-lookup"><span data-stu-id="5ced3-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="5ced3-113">Bezorgingsgroep met hoog risico</span><span class="sxs-lookup"><span data-stu-id="5ced3-113">High-risk delivery pool</span></span>
<span data-ttu-id="5ced3-114">Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365 datacenterservers die zijn vastgesteld dat ze spam zijn of die de verzendende limieten van het [service-](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de groep met een hoog _risico._</span><span class="sxs-lookup"><span data-stu-id="5ced3-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="5ced3-115">De groep bezorging met hoog risico is een aparte IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van 'lage kwaliteit' te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="5ced3-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="5ced3-116">Als u de groep met een hoog risico gebruikt, voorkomt u dat de normale IP-adresgroep voor uitgaande e-mail spam verstuurt.</span><span class="sxs-lookup"><span data-stu-id="5ced3-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="5ced3-117">De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie van het verzenden van berichten van hoge kwaliteit, waardoor de kans wordt verkleind dat dit IP-adres wordt weergegeven in IP-blokkeringen.</span><span class="sxs-lookup"><span data-stu-id="5ced3-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="5ced3-118">De zeer reële mogelijkheid dat IP-adressen in de groep met een hoog risico worden geplaatst op IP-blokkeringen blijft bestaan, maar dit is een ontwerp.</span><span class="sxs-lookup"><span data-stu-id="5ced3-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="5ced3-119">Bezorging aan de beoogde geadresseerden is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de groep met hoge risico's.</span><span class="sxs-lookup"><span data-stu-id="5ced3-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="5ced3-120">Zie Uitgaande spam controleren [voor meer informatie.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="5ced3-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ced3-121">Berichten waarin het bron-e-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd door de groep met hoge risico's verzonden, ongeacht de spam of het verzenden van limieten.</span><span class="sxs-lookup"><span data-stu-id="5ced3-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="5ced3-122">Berichten bouncen</span><span class="sxs-lookup"><span data-stu-id="5ced3-122">Bounce messages</span></span>

<span data-ttu-id="5ced3-123">De groep uitgaande bezorging met hoog risico beheert de bezorging voor alle niet-bezorgingsrapporten (ook wel NDR's genoemd, niet-bezorgdberichten, meldingen over de bezorgingsstatus of DSN's).</span><span class="sxs-lookup"><span data-stu-id="5ced3-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="5ced3-124">Mogelijke oorzaken voor een toename van NDR's zijn:</span><span class="sxs-lookup"><span data-stu-id="5ced3-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="5ced3-125">Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5ced3-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="5ced3-126">Een directory oogst aanval.</span><span class="sxs-lookup"><span data-stu-id="5ced3-126">A directory harvest attack.</span></span>
- <span data-ttu-id="5ced3-127">Een spam-aanval.</span><span class="sxs-lookup"><span data-stu-id="5ced3-127">A spam attack.</span></span>
- <span data-ttu-id="5ced3-128">Een malafide e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="5ced3-128">A rogue email server.</span></span>

<span data-ttu-id="5ced3-129">Al deze problemen kunnen leiden tot een plotse toename van het aantal NR's dat door de service wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="5ced3-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="5ced3-130">Vaak lijken deze NR's spam te zijn naar andere e-mailservers en -services (ook wel _[backscatter genoemd).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="5ced3-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="5ced3-131">Relaisgroep</span><span class="sxs-lookup"><span data-stu-id="5ced3-131">Relay pool</span></span>

<span data-ttu-id="5ced3-132">Berichten die in bepaalde scenario's via Microsoft 365 worden doorgestuurd of doorgestuurd, worden verzonden met een speciale relaisgroep, omdat de bestemming de Microsoft 365 niet moet beschouwen als de werkelijke afzender.</span><span class="sxs-lookup"><span data-stu-id="5ced3-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="5ced3-133">Het is belangrijk dat we dit e-mailverkeer isoleren, omdat er legitieme en ongeldige scenario's zijn voor het automatisch doorsturen of doorsturen van e-mail Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ced3-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="5ced3-134">Net als bij de groep met een hoog risico wordt een aparte IP-adresgroep gebruikt voor doorgestuurde e-mail.</span><span class="sxs-lookup"><span data-stu-id="5ced3-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="5ced3-135">Deze adresgroep wordt niet gepubliceerd omdat deze vaak kan worden gewijzigd en het maakt geen deel uit van de gepubliceerde SPF-record voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ced3-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="5ced3-136">Microsoft 365 moet controleren of de oorspronkelijke afzender legitiem is, zodat we het doorgestuurde bericht met vertrouwen kunnen bezorgen.</span><span class="sxs-lookup"><span data-stu-id="5ced3-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="5ced3-137">Het doorgestuurde/doorgestuurde bericht moet voldoen aan een van de volgende criteria om te voorkomen dat de doorgestuurde groep wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="5ced3-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="5ced3-138">De uitgaande afzender is in een [geaccepteerd domein.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="5ced3-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="5ced3-139">SPF wordt pas weergegeven wanneer het bericht wordt Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ced3-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="5ced3-140">DKIM op het afzenderdomein wordt weergegeven wanneer het bericht wordt Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ced3-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="5ced3-141">U kunt zien dat een bericht is verzonden via de relaygroep door te kijken naar het IP-adres van de uitgaande server (de relaisgroep zal zich in het bereik 40.95.0.0/16) of door te kijken naar de naam van de uitgaande server (er staat 'rly' in de naam).</span><span class="sxs-lookup"><span data-stu-id="5ced3-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="5ced3-142">In gevallen waarin we de afzender kunnen verifiëren, gebruiken we Sender Rewriting Scheme (SRS) om het e-mailsysteem van de geadresseerde te helpen weten dat het doorgestuurde bericht afkomstig is van een vertrouwde bron.</span><span class="sxs-lookup"><span data-stu-id="5ced3-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="5ced3-143">U kunt meer lezen over hoe dat werkt en wat u kunt doen om ervoor te zorgen dat het verzendende domein verificatie doorstaat in [Sender Rewriting Scheme (SRS) in Office 365.](/office365/troubleshoot/antispam/sender-rewriting-scheme)</span><span class="sxs-lookup"><span data-stu-id="5ced3-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="5ced3-144">Als DKIM werkt, moet u DKIM inschakelen voor het verzenden van domein.</span><span class="sxs-lookup"><span data-stu-id="5ced3-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="5ced3-145">De fabrikam.com maakt bijvoorbeeld deel uit van contoso.com en wordt gedefinieerd in de geaccepteerde domeinen van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5ced3-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="5ced3-146">Als de afzender van het bericht sender@fabrikam.com, moet DKIM zijn ingeschakeld voor fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5ced3-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="5ced3-147">U kunt lezen hoe u [DKIM](use-dkim-to-validate-outbound-email.md)kunt inschakelen om uitgaande e-mail te valideren die is verzonden vanuit uw aangepaste domein.</span><span class="sxs-lookup"><span data-stu-id="5ced3-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="5ced3-148">Als u een aangepast domein wilt toevoegen, volgt u de stappen in [Een domein toevoegen aan Microsoft 365.](../../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="5ced3-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
