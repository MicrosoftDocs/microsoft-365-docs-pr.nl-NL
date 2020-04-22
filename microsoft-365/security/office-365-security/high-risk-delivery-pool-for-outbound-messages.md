---
title: Groep met verhoogd risico voor uitgaande berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Ontdek hoe de leveringspool met een hoog risico wordt gebruikt om de reputatie van e-mailservers in de Microsoft 365-datacenters te beschermen.
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638032"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="e168a-103">Groep met verhoogd risico voor uitgaande berichten</span><span class="sxs-lookup"><span data-stu-id="e168a-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="e168a-104">E-mailservers in de Microsoft 365-datacenters maken zich mogelijk tijdelijk schuldig aan het verzenden van spam.</span><span class="sxs-lookup"><span data-stu-id="e168a-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="e168a-105">Bijvoorbeeld een malware- of schadelijke spamaanval in een on-premises e-mailorganisatie die uitgaande e-mail verzendt via Microsoft 365 of microsoft 365-accounts heeft gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="e168a-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="e168a-106">Deze scenario's kunnen ertoe leiden dat het IP-adres van de getroffen Microsoft 365-datacenterservers wordt weergegeven op bloklijsten van derden.</span><span class="sxs-lookup"><span data-stu-id="e168a-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="e168a-107">Bestemmingse-e-mailorganisaties die deze bloklijsten gebruiken, weigeren e-mail van deze berichtenbronnen.</span><span class="sxs-lookup"><span data-stu-id="e168a-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="e168a-108">Om dit te voorkomen, worden alle uitgaande berichten van Microsoft 365-datacenterservers waarvan is vastgesteld dat ze spam zijn of die de verzendlimieten van [de service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of het [uitgaande spambeleid](configure-the-outbound-spam-policy.md) overschrijden, verzonden via de _groep voor levering met een hoog risico._</span><span class="sxs-lookup"><span data-stu-id="e168a-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="e168a-109">De groep voor levering met een hoog risico is een secundaire IP-adresgroep voor uitgaande e-mail die alleen wordt gebruikt om berichten van "lage kwaliteit" te verzenden (bijvoorbeeld spam en [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="e168a-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="e168a-110">Als u de groep voor levering met een hoog risico gebruikt, voorkomt u dat de normale IP-adresgroep voor uitgaande e-mail spam verzendt.</span><span class="sxs-lookup"><span data-stu-id="e168a-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="e168a-111">De normale IP-adresgroep voor uitgaande e-mail behoudt de reputatie die berichten van "hoge kwaliteit" verzendt, waardoor de kans kleiner is dat dit IP-adres op IP-bloklijsten wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e168a-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="e168a-112">De zeer reële mogelijkheid dat IP-adressen in de risicogroep worden geplaatst op IP-bloklijsten blijft bestaan, maar dit is door het ontwerp.</span><span class="sxs-lookup"><span data-stu-id="e168a-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="e168a-113">Levering aan de beoogde ontvangers is niet gegarandeerd, omdat veel e-mailorganisaties geen berichten accepteren uit de groep voor levering met een hoog risico.</span><span class="sxs-lookup"><span data-stu-id="e168a-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="e168a-114">Zie [Outbound Spam beheren](outbound-spam-controls.md)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="e168a-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e168a-115">Berichten waarbij het brone-maildomein geen A-record heeft en geen MX-record die is gedefinieerd in openbare DNS, worden altijd door de groep met een hoog risico geleid, ongeacht hun spam of het verzenden van limietdispositie.</span><span class="sxs-lookup"><span data-stu-id="e168a-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="e168a-116">Bounceberichten</span><span class="sxs-lookup"><span data-stu-id="e168a-116">Bounce messages</span></span>

<span data-ttu-id="e168a-117">De uitgaande delivery pool met hoog risico beheert de levering voor alle niet-leveringsrapporten (ook bekend als NDR's, bounceberichten, meldingen over de leveringsstatus of DSN's).</span><span class="sxs-lookup"><span data-stu-id="e168a-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="e168a-118">Mogelijke oorzaken voor een stijging van de NDR's zijn:</span><span class="sxs-lookup"><span data-stu-id="e168a-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="e168a-119">Een spoofing-campagne die van invloed is op een van de klanten die de service gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e168a-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="e168a-120">Een directory oogst aanval.</span><span class="sxs-lookup"><span data-stu-id="e168a-120">A directory harvest attack.</span></span>

- <span data-ttu-id="e168a-121">Een spamaanval.</span><span class="sxs-lookup"><span data-stu-id="e168a-121">A spam attack.</span></span>

- <span data-ttu-id="e168a-122">Een malafide e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="e168a-122">A rogue email server.</span></span>

<span data-ttu-id="e168a-123">Al deze problemen kunnen resulteren in een plotselinge toename van het aantal NDR's dat door de service wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="e168a-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="e168a-124">Vele malen, deze NDR's lijken te zijn spam naar andere e-mailservers en diensten (ook wel bekend als _[backscatter).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="e168a-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
