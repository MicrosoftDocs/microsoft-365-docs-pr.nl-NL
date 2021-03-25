---
title: Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing
description: Gebruik de onderzoeksopties om mogelijke communicatie tussen apparaten en externe IP-adressen te onderzoeken.
keywords: onderzoeken, IP-adres, waarschuwing, microsoft defender atp, extern IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 003abd854e34bb5a9a05f675313ba6c4f6ce1d71
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186039"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="d3b91-104">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="d3b91-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d3b91-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d3b91-105">**Applies to:**</span></span>
- [<span data-ttu-id="d3b91-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3b91-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d3b91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3b91-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="d3b91-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d3b91-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d3b91-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d3b91-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d3b91-110">Bekijk mogelijke communicatie tussen uw apparaten en IP-adressen (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="d3b91-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="d3b91-111">Het identificeren van alle apparaten in de organisatie die hebben gecommuniceerd met een verdacht of bekend schadelijk IP-adres, zoals C2-servers (Command and Control), helpt bij het bepalen van het mogelijke bereik van inbreuk, bijbehorende bestanden en geïnfecteerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="d3b91-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="d3b91-112">U vindt informatie uit de volgende secties in de IP-adresweergave:</span><span class="sxs-lookup"><span data-stu-id="d3b91-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="d3b91-113">IP wereldwijd</span><span class="sxs-lookup"><span data-stu-id="d3b91-113">IP worldwide</span></span>
- <span data-ttu-id="d3b91-114">DNS-namen omkeren</span><span class="sxs-lookup"><span data-stu-id="d3b91-114">Reverse DNS names</span></span>
- <span data-ttu-id="d3b91-115">Waarschuwingen met betrekking tot dit IP-adres</span><span class="sxs-lookup"><span data-stu-id="d3b91-115">Alerts related to this IP</span></span>
- <span data-ttu-id="d3b91-116">IP in organisatie</span><span class="sxs-lookup"><span data-stu-id="d3b91-116">IP in organization</span></span>
- <span data-ttu-id="d3b91-117">Prevalentie</span><span class="sxs-lookup"><span data-stu-id="d3b91-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="d3b91-118">IP Worldwide en Reverse DNS-namen</span><span class="sxs-lookup"><span data-stu-id="d3b91-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="d3b91-119">De sectie IP-adresgegevens bevat kenmerken van het IP-adres, zoals het ASN en de reverse DNS-namen.</span><span class="sxs-lookup"><span data-stu-id="d3b91-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="d3b91-120">Waarschuwingen met betrekking tot dit IP-adres</span><span class="sxs-lookup"><span data-stu-id="d3b91-120">Alerts related to this IP</span></span>

<span data-ttu-id="d3b91-121">De **sectie Waarschuwingen met betrekking tot deze IP-sectie** bevat een lijst met waarschuwingen die aan het IP-adres zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d3b91-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="d3b91-122">IP in organisatie</span><span class="sxs-lookup"><span data-stu-id="d3b91-122">IP in organization</span></span>

<span data-ttu-id="d3b91-123">De **sectie IP in organisatie** bevat details over de prevalentie van het IP-adres in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d3b91-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="d3b91-124">Prevalentie</span><span class="sxs-lookup"><span data-stu-id="d3b91-124">Prevalence</span></span>

<span data-ttu-id="d3b91-125">In **de sectie Prevalentie** wordt weergegeven hoeveel apparaten zijn verbonden met dit IP-adres en wanneer het IP-adres voor het eerst en voor het laatst is gezien.</span><span class="sxs-lookup"><span data-stu-id="d3b91-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="d3b91-126">U kunt de resultaten van deze sectie filteren op tijdsperiode. de standaardperiode is 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="d3b91-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="d3b91-127">Meest recente waargenomen apparaten met IP</span><span class="sxs-lookup"><span data-stu-id="d3b91-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="d3b91-128">De **sectie Meest recente waargenomen apparaten** met IP-adres biedt een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op het IP-adres.</span><span class="sxs-lookup"><span data-stu-id="d3b91-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="d3b91-129">**Een extern IP-adres onderzoeken:**</span><span class="sxs-lookup"><span data-stu-id="d3b91-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="d3b91-130">Selecteer **IP** in **de** vervolgkeuzelijst Zoekbalk.</span><span class="sxs-lookup"><span data-stu-id="d3b91-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="d3b91-131">Voer het IP-adres in het **veld Zoeken** in.</span><span class="sxs-lookup"><span data-stu-id="d3b91-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="d3b91-132">Klik op het zoekpictogram of druk op **Enter.**</span><span class="sxs-lookup"><span data-stu-id="d3b91-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="d3b91-133">Details over het IP-adres worden weergegeven, waaronder: registratiedetails (indien beschikbaar), reverse-IP's (bijvoorbeeld domeinen), de aanwezigheid van apparaten in de organisatie die met dit IP-adres hebben gecommuniceerd (tijdens een selecteerbare periode) en de apparaten in de organisatie die met dit IP-adres zijn gecommuniceerd.</span><span class="sxs-lookup"><span data-stu-id="d3b91-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="d3b91-134">Zoekresultaten worden alleen geretourneerd voor IP-adressen die worden waargenomen in communicatie met apparaten in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d3b91-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="d3b91-135">Gebruik de zoekfilters om de zoekcriteria te definiëren.</span><span class="sxs-lookup"><span data-stu-id="d3b91-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="d3b91-136">U kunt ook het zoekvak voor de tijdlijn gebruiken om de weergegeven resultaten te filteren van alle apparaten in de organisatie die zijn waargenomen bij het communiceren met het IP-adres, het bestand dat is gekoppeld aan de communicatie en de laatste waargenomen datum.</span><span class="sxs-lookup"><span data-stu-id="d3b91-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="d3b91-137">Als u op een van de apparaatnamen klikt, gaat u naar de weergave van dat apparaat, waar u gerapporteerde waarschuwingen, gedragingen en gebeurtenissen kunt blijven onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="d3b91-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3b91-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d3b91-138">Related topics</span></span>

- [<span data-ttu-id="d3b91-139">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="d3b91-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="d3b91-140">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="d3b91-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="d3b91-141">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="d3b91-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="d3b91-142">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="d3b91-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="d3b91-143">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="d3b91-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="d3b91-144">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="d3b91-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="d3b91-145">Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d3b91-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
