---
title: NAT-ondersteuning met Office 365
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
description: In dit artikel vindt u meer informatie over hoe u het aantal clients per IP-adres in uw organisatie met NAT kunt gebruiken.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688944"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="3bb65-103">NAT-ondersteuning met Office 365</span><span class="sxs-lookup"><span data-stu-id="3bb65-103">NAT support with Office 365</span></span>

<span data-ttu-id="3bb65-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3bb65-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3bb65-105">Eerder werd u aangeraden het maximale aantal Exchange-clients per IP-adres te gebruiken om verbinding te maken met Office 365 via 2.000 clients per netwerkpoort.</span><span class="sxs-lookup"><span data-stu-id="3bb65-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="3bb65-106">Het nut van NAT</span><span class="sxs-lookup"><span data-stu-id="3bb65-106">Why use NAT?</span></span>

<span data-ttu-id="3bb65-107">Met behulp van NAT kunnen duizenden personen in een bedrijfsnetwerk ' delen ' een paar openbaar routerende IP-adressen delen.</span><span class="sxs-lookup"><span data-stu-id="3bb65-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="3bb65-108">In de meeste bedrijfsnetwerken wordt de IP-adresruimte van private (RFC1918) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3bb65-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="3bb65-109">Persoonlijke adresruimte wordt toegewezen door de beheerder van Internet toegewezen nummers (IANA) en uitsluitend bedoeld voor netwerken die niet rechtstreeks naar en via het globale Internet worden gerouteerd.</span><span class="sxs-lookup"><span data-stu-id="3bb65-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="3bb65-110">Voor het verlenen van toegang tot apparaten via een persoonlijke IP-adresruimte kunnen organisaties gebruikmaken van gateway technologieën zoals firewalls en proxy's die netwerkadresomzetting (NAT) of netwerkadresomzetting (netwerkadresomzetting) bieden.</span><span class="sxs-lookup"><span data-stu-id="3bb65-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="3bb65-111">Deze gateways zorgen dat verkeer van interne apparaten naar Internet (waaronder Office 365) afkomstig is van een of meer openbaar routeerbaarere IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="3bb65-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="3bb65-112">Elke uitgaande verbinding van een intern apparaat wordt omgezet in een andere bron-TCP-poort voor het openbare IP-adres.</span><span class="sxs-lookup"><span data-stu-id="3bb65-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="3bb65-113">Waarom moet u ervoor zorgen dat er meerdere verbindingen tegelijk met Office 365 worden geopend?</span><span class="sxs-lookup"><span data-stu-id="3bb65-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="3bb65-114">In Outlook worden acht of meer verbindingen geopend (in situaties waarin er invoegtoepassingen zijn, gedeelde agenda's, postvakken, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="3bb65-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="3bb65-115">Aangezien er maximaal 64.000 poorten beschikbaar zijn op een op Windows gebaseerd NAT-apparaat, kunnen er maximaal 8.000 gebruikers achter een IP-adres worden weergegeven voordat de poorten zijn uitgeput.</span><span class="sxs-lookup"><span data-stu-id="3bb65-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="3bb65-116">Als klanten niet-Windows-besturingssystemen op basis van de NAT gebruiken, zijn de totale beschikbare poorten afhankelijk van welk NAT-apparaat of welke software wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3bb65-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="3bb65-117">In dit scenario kon het maximum aantal poorten kleiner zijn dan 64.000.</span><span class="sxs-lookup"><span data-stu-id="3bb65-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="3bb65-118">De beschikbaarheid van poorten wordt ook beïnvloed door andere factoren, zoals Windows-beperkingen voor 4.000-poorten voor eigen gebruik, waardoor het totale aantal beschikbare poorten wordt beperkt tot 60.000.</span><span class="sxs-lookup"><span data-stu-id="3bb65-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="3bb65-119">Er kunnen andere toepassingen zijn, zoals Internet Explorer, die tegelijk verbinding konden maken, zodat er extra poorten zijn.</span><span class="sxs-lookup"><span data-stu-id="3bb65-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="3bb65-120">Het maximum aantal ondersteunde apparaten per openbaar IP-adres berekenen met Office 365</span><span class="sxs-lookup"><span data-stu-id="3bb65-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="3bb65-121">Als u het maximum aantal apparaten achter één openbaar IP-adres wilt bepalen, dient u netwerkverkeer te controleren om het piek poort verbruik per client te bepalen.</span><span class="sxs-lookup"><span data-stu-id="3bb65-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="3bb65-122">Daarnaast moet een piek factor worden gebruikt voor het poort gebruik (minimaal 4).</span><span class="sxs-lookup"><span data-stu-id="3bb65-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="3bb65-123">**Gebruik de volgende formule voor het berekenen van het aantal ondersteunde apparaten per IP-adres:**</span><span class="sxs-lookup"><span data-stu-id="3bb65-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="3bb65-124">Maximum aantal ondersteunde apparaten per openbaar IP-adres = (64.000-beperkte poorten)/(piek poort verbruik + piek factor)</span><span class="sxs-lookup"><span data-stu-id="3bb65-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="3bb65-125">**Als u bijvoorbeeld de volgende beweringen waar is:**</span><span class="sxs-lookup"><span data-stu-id="3bb65-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="3bb65-126">**Beperkte poorten:** 4.000 voor het besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="3bb65-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="3bb65-127">**Piek verbruik van poort:** 6 per apparaat</span><span class="sxs-lookup"><span data-stu-id="3bb65-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="3bb65-128">**Piek factor:** 4</span><span class="sxs-lookup"><span data-stu-id="3bb65-128">**Peak factor:** 4</span></span>

<span data-ttu-id="3bb65-129">Vervolgens worden de maximum aantal ondersteunde apparaten achter één openbaar IP-adres = (64.000-4000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="3bb65-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="3bb65-130">Met de release van het Office 365-hosting pakket, dat deel uitmaakt van de updates van september 2011 voor Microsoft Office Outlook 2007 of november 2011 voor Microsoft Outlook of een latere update, kan het aantal verbindingen vanuit Outlook (zowel Office Outlook 2010 met Service Pack 2 en Outlook 2007) niet worden gebruikt voor Exchange.</span><span class="sxs-lookup"><span data-stu-id="3bb65-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="3bb65-131">U moet een factor opgeven voor de verschillende besturingssystemen, gebruikersgedrag en om het minimum en maximum aantal poorten te bepalen dat uw netwerk nodig heeft op piek.</span><span class="sxs-lookup"><span data-stu-id="3bb65-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="3bb65-132">Als u meer apparaten wilt ondersteunen achter één openbaar IP-adres, volgt u de stappen voor het bepalen van het maximum aantal apparaten dat kan worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="3bb65-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="3bb65-133">Controleer netwerkverkeer om het piek poort verbruik per client te bepalen.</span><span class="sxs-lookup"><span data-stu-id="3bb65-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="3bb65-134">U dient deze gegevens te verzamelen:</span><span class="sxs-lookup"><span data-stu-id="3bb65-134">You should collect this data:</span></span>
  
- <span data-ttu-id="3bb65-135">Vanaf meerdere locaties</span><span class="sxs-lookup"><span data-stu-id="3bb65-135">From multiple locations</span></span>
    
- <span data-ttu-id="3bb65-136">Vanaf meerdere apparaten</span><span class="sxs-lookup"><span data-stu-id="3bb65-136">From multiple devices</span></span>
    
- <span data-ttu-id="3bb65-137">Op meerdere momenten</span><span class="sxs-lookup"><span data-stu-id="3bb65-137">At multiple times</span></span>
    
<span data-ttu-id="3bb65-138">Gebruik de bovenstaande formule voor het berekenen van het maximum aantal gebruikers per IP-adres dat wordt ondersteund in de omgeving.</span><span class="sxs-lookup"><span data-stu-id="3bb65-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="3bb65-139">Er zijn verschillende manieren om de belasting van de client te verdelen over extra openbare IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="3bb65-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="3bb65-140">Welke strategieën beschikbaar zijn, is afhankelijk van de mogelijkheden van de corporate Gateway-oplossing.</span><span class="sxs-lookup"><span data-stu-id="3bb65-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="3bb65-141">De eenvoudigste oplossing is het segmenteren van de adresruimte van uw gebruikers en het statisch toewijzen van een aantal IP-adressen aan elke gateway.</span><span class="sxs-lookup"><span data-stu-id="3bb65-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="3bb65-142">U kunt ook een groep IP-adressen gebruiken om een andere optie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3bb65-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="3bb65-143">Het voordeel van de adresgroep is dat het veel dynamischer en minder waarschijnlijk moet worden aangepast naarmate de basis van de gebruikers breidt.</span><span class="sxs-lookup"><span data-stu-id="3bb65-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bb65-144">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3bb65-144">See also</span></span>

[<span data-ttu-id="3bb65-145">Office 365-eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="3bb65-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="3bb65-146">Veelgestelde vragen over Office 365-eindpunten</span><span class="sxs-lookup"><span data-stu-id="3bb65-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
