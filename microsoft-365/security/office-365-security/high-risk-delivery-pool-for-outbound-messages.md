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
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599909"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="d0531-103">Uitgaande bezorgingspools</span><span class="sxs-lookup"><span data-stu-id="d0531-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d0531-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d0531-104">**Applies to**</span></span>
- [<span data-ttu-id="d0531-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d0531-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d0531-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d0531-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d0531-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0531-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d0531-108">E-mailservers in Microsoft 365 datacenters zijn mogelijk tijdelijk schuldig aan het verzenden van spam.</span><span class="sxs-lookup"><span data-stu-id="d0531-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="d0531-109">Bijvoorbeeld een malware- of schadelijke spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of gecompromitteerde Microsoft 365 accounts.</span><span class="sxs-lookup"><span data-stu-id="d0531-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="d0531-110">Aanvallers proberen detectie ook te voorkomen door berichten door te sturen via Microsoft 365 doorsturen.</span><span class="sxs-lookup"><span data-stu-id="d0531-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="d0531-111">Deze scenario's kunnen resulteren in het IP-adres van de Microsoft 365 datacenterservers die worden weergegeven op blokkeringen van derden.</span><span class="sxs-lookup"><span data-stu-id="d0531-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="d0531-112">Doel-e-mailorganisaties die deze blokkeringen gebruiken, weigeren e-mail uit deze berichtenbronnen.</span><span class="sxs-lookup"><span data-stu-id="d0531-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="d0531-113">Bezorgingsgroep met hoog risico</span><span class="sxs-lookup"><span data-stu-id="d0531-113">High-risk delivery pool</span></span>
<span data-ttu-id="d0531-114">Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365 datacenterservers die zijn vastgesteld dat ze spam zijn of die de verzendende limieten van het [service-](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of uitgaande [spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de groep met een hoog _risico._</span><span class="sxs-lookup"><span data-stu-id="d0531-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="d0531-115">De groep bezorging met hoog risico is een aparte IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van 'lage kwaliteit' te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d0531-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="d0531-116">Als u de groep met een hoog risico gebruikt, voorkomt u dat de normale IP-adresgroep voor uitgaande e-mail spam verstuurt.</span><span class="sxs-lookup"><span data-stu-id="d0531-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="d0531-117">De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie van het verzenden van berichten van hoge kwaliteit, waardoor de kans wordt verkleind dat dit IP-adres wordt weergegeven in IP-blokkeringen.</span><span class="sxs-lookup"><span data-stu-id="d0531-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="d0531-118">De zeer reële mogelijkheid dat IP-adressen in de groep met een hoog risico worden geplaatst op IP-blokkeringen blijft bestaan, maar dit is een ontwerp.</span><span class="sxs-lookup"><span data-stu-id="d0531-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="d0531-119">Bezorging aan de beoogde geadresseerden is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de groep met hoge risico's.</span><span class="sxs-lookup"><span data-stu-id="d0531-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="d0531-120">Zie Uitgaande spam controleren [voor meer informatie.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="d0531-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0531-121">Berichten waarin het bron-e-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd door de groep met hoge risico's verzonden, ongeacht de spam of het verzenden van limieten.</span><span class="sxs-lookup"><span data-stu-id="d0531-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="d0531-122">Berichten bouncen</span><span class="sxs-lookup"><span data-stu-id="d0531-122">Bounce messages</span></span>

<span data-ttu-id="d0531-123">De groep uitgaande bezorging met hoog risico beheert de bezorging voor alle niet-bezorgingsrapporten (ook wel NDR's genoemd, niet-bezorgdberichten, meldingen over de bezorgingsstatus of DSN's).</span><span class="sxs-lookup"><span data-stu-id="d0531-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="d0531-124">Mogelijke oorzaken voor een toename van NDR's zijn:</span><span class="sxs-lookup"><span data-stu-id="d0531-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="d0531-125">Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d0531-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="d0531-126">Een directory oogst aanval.</span><span class="sxs-lookup"><span data-stu-id="d0531-126">A directory harvest attack.</span></span>
- <span data-ttu-id="d0531-127">Een spam-aanval.</span><span class="sxs-lookup"><span data-stu-id="d0531-127">A spam attack.</span></span>
- <span data-ttu-id="d0531-128">Een malafide e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="d0531-128">A rogue email server.</span></span>

<span data-ttu-id="d0531-129">Al deze problemen kunnen leiden tot een plotse toename van het aantal NR's dat door de service wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="d0531-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="d0531-130">Vaak lijken deze NR's spam te zijn naar andere e-mailservers en -services (ook wel _[backscatter genoemd).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="d0531-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
