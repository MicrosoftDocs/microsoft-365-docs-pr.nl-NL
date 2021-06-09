---
title: Ondersteuning voor NAT met Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: In dit artikel vindt u informatie over het benaderen van het aantal clients dat u per IP-adres in uw organisatie kunt gebruiken met NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688944"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="7a2d4-103">Ondersteuning voor NAT met Office 365</span><span class="sxs-lookup"><span data-stu-id="7a2d4-103">NAT support with Office 365</span></span>

<span data-ttu-id="7a2d4-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7a2d4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7a2d4-105">Eerder werd voorgesteld dat het maximum aantal Exchange clients dat u per IP-adres moet gebruiken om verbinding te maken met Office 365 ongeveer 2.000 clients per netwerkpoort was.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="7a2d4-106">Waarom NAT gebruiken?</span><span class="sxs-lookup"><span data-stu-id="7a2d4-106">Why use NAT?</span></span>

<span data-ttu-id="7a2d4-107">Met NAT kunnen duizenden personen in een bedrijfsnetwerk een paar openbare IP-adressen 'delen'.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="7a2d4-108">De meeste bedrijfsnetwerken gebruiken persoonlijke IP-adresruimte (RFC1918).</span><span class="sxs-lookup"><span data-stu-id="7a2d4-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="7a2d4-109">Persoonlijke adresruimte wordt toegewezen door de Internet Assigned Numbers Authority (IANA) en is uitsluitend bedoeld voor netwerken die niet rechtstreeks van en naar het globale internet worden gerouteerd.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="7a2d4-110">Als u internettoegang wilt bieden tot apparaten op een privé-IP-adresruimte, gebruiken organisaties gatewaytechnologieën zoals firewalls en proxies die nat- of poortadresvertalingsservices (NETWORK Address Translation) bieden.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="7a2d4-111">Met deze gateways lijkt het verkeer van interne apparaten naar internet (inclusief Office 365) afkomstig te zijn van een of meer openbare IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="7a2d4-112">Elke uitgaande verbinding van een intern apparaat wordt vertaald naar een andere bron-TCP-poort op het openbare IP-adres.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="7a2d4-113">Waarom moeten er zoveel verbindingen tegelijk Office 365?</span><span class="sxs-lookup"><span data-stu-id="7a2d4-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="7a2d4-114">Outlook kan acht of meer verbindingen openen (in situaties waarin er invoegvoegingen, gedeelde agenda's, postvakken, enzovoort zijn).</span><span class="sxs-lookup"><span data-stu-id="7a2d4-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="7a2d4-115">Omdat er maximaal 64.000 poorten beschikbaar zijn op een nat-apparaat op basis van Windows, kunnen er maximaal 8.000 gebruikers achter een IP-adres zitten voordat de poorten leeg zijn.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="7a2d4-116">Houd er rekening mee dat als klanten niet-Windows voor NAT gebruiken, de totale beschikbare poorten afhankelijk zijn van welk NAT-apparaat of welke software wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="7a2d4-117">In dit scenario kan het maximum aantal poorten kleiner zijn dan 64.000.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="7a2d4-118">De beschikbaarheid van poorten wordt ook beïnvloed door andere factoren, zoals Windows het beperken van 4.000 poorten voor eigen gebruik, waardoor het totale aantal beschikbare poorten wordt beperkt tot 60.000.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="7a2d4-119">Er kunnen andere toepassingen zijn, zoals Internet Explorer, die tegelijkertijd verbinding kunnen maken, waarvoor extra poorten nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="7a2d4-120">Maximaal ondersteunde apparaten berekenen achter één openbaar IP-adres met Office 365</span><span class="sxs-lookup"><span data-stu-id="7a2d4-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="7a2d4-121">Als u het maximum aantal apparaten achter één openbaar IP-adres wilt bepalen, moet u netwerkverkeer controleren om het piekportverbruik per client te bepalen.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="7a2d4-122">Ook moet een piekfactor worden gebruikt voor het poortgebruik (minimaal 4).</span><span class="sxs-lookup"><span data-stu-id="7a2d4-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="7a2d4-123">**Gebruik de volgende formule om het aantal ondersteunde apparaten per IP-adres te berekenen:**</span><span class="sxs-lookup"><span data-stu-id="7a2d4-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="7a2d4-124">Maximaal ondersteunde apparaten achter één openbaar IP-adres = (64.000 - beperkte poorten)/(Piekpoortverbruik + piekfactor)</span><span class="sxs-lookup"><span data-stu-id="7a2d4-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="7a2d4-125">**Als bijvoorbeeld het volgende waar is:**</span><span class="sxs-lookup"><span data-stu-id="7a2d4-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="7a2d4-126">**Beperkte poorten:** 4.000 voor het besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="7a2d4-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="7a2d4-127">**Piekpoortverbruik:** 6 per apparaat</span><span class="sxs-lookup"><span data-stu-id="7a2d4-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="7a2d4-128">**Piekfactor:** 4</span><span class="sxs-lookup"><span data-stu-id="7a2d4-128">**Peak factor:** 4</span></span>

<span data-ttu-id="7a2d4-129">Vervolgens worden de maximaal ondersteunde apparaten achter één openbaar IP-adres = (64.000 - 4.000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="7a2d4-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="7a2d4-130">Met de release van Office 365 hostingpack, opgenomen in de updates van september 2011 voor Microsoft Office Outlook 2007 of november 2011 voor Microsoft Outlook 2010 of een latere update, kan het aantal verbindingen uit Outlook (zowel Office Outlook 2007 met Service Pack 2 als Outlook 2010) tot Exchange slechts 2 zijn.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="7a2d4-131">U moet rekening houden met de verschillende besturingssystemen, gebruikersgedrag, en ga zo maar door om het minimum- en maximumaantal poorten te bepalen dat uw netwerk op piekmomenten nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="7a2d4-132">Als u meer apparaten achter één openbaar IP-adres wilt ondersteunen, volgt u de stappen die worden beschreven om het maximum aantal apparaten te beoordelen dat kan worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="7a2d4-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="7a2d4-133">Houd netwerkverkeer in de gaten om het piekverbruik per client te bepalen.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="7a2d4-134">U moet deze gegevens verzamelen:</span><span class="sxs-lookup"><span data-stu-id="7a2d4-134">You should collect this data:</span></span>
  
- <span data-ttu-id="7a2d4-135">Vanuit meerdere locaties</span><span class="sxs-lookup"><span data-stu-id="7a2d4-135">From multiple locations</span></span>
    
- <span data-ttu-id="7a2d4-136">Vanaf meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="7a2d4-136">From multiple devices</span></span>
    
- <span data-ttu-id="7a2d4-137">Op meerdere momenten</span><span class="sxs-lookup"><span data-stu-id="7a2d4-137">At multiple times</span></span>
    
<span data-ttu-id="7a2d4-138">Gebruik de voorgaande formule om de maximale gebruikers per IP-adres te berekenen die in hun omgeving kunnen worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="7a2d4-139">Er zijn verschillende methoden voor het distribueren van clientbelasting over extra openbare IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="7a2d4-140">Beschikbare strategieën zijn afhankelijk van de mogelijkheden van de bedrijfsgatewayoplossing.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="7a2d4-141">De eenvoudigste oplossing is om uw gebruikersadresruimte te segmenteren en statisch een aantal IP-adressen aan elke gateway toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="7a2d4-142">Een ander alternatief dat veel gateway-apparaten bieden, is de mogelijkheid om een groep IP-adressen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="7a2d4-143">Het voordeel van de adresgroep is dat deze veel dynamischer is en minder waarschijnlijk aanpassing nodig heeft naarmate uw gebruikersbestand groeit.</span><span class="sxs-lookup"><span data-stu-id="7a2d4-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a2d4-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7a2d4-144">See also</span></span>

[<span data-ttu-id="7a2d4-145">Office 365-eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="7a2d4-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="7a2d4-146">Veelgestelde vragen over Office 365-eindpunten</span><span class="sxs-lookup"><span data-stu-id="7a2d4-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
