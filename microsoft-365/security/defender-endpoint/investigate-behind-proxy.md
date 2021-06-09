---
title: Verbindingsgebeurtenissen achter forward-proxies onderzoeken
description: Meer informatie over het gebruik van geavanceerde http-niveaucontrole via netwerkbeveiliging in Microsoft Defender voor Eindpunt, waarmee een reëel doel wordt bereikt in plaats van een proxy.
keywords: proxy, netwerkbeveiliging, doorgestuurde proxy, netwerkgebeurtenissen, audit, blok, domeinnamen, domein
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 55c001781ff016d7a23dc5db286d454b39fac5de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841052"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="ef81a-104">Verbindingsgebeurtenissen achter forward-proxies onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ef81a-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ef81a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ef81a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ef81a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ef81a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ef81a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef81a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ef81a-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ef81a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ef81a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ef81a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="ef81a-110">Defender voor Eindpunt ondersteunt netwerkverbindingsmonitoring vanaf verschillende niveaus van de netwerkstapel.</span><span class="sxs-lookup"><span data-stu-id="ef81a-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="ef81a-111">Een lastig geval is dat het netwerk een doorgestuurde proxy gebruikt als gateway naar internet.</span><span class="sxs-lookup"><span data-stu-id="ef81a-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="ef81a-112">De proxy doet alsof deze het doel-eindpunt is.</span><span class="sxs-lookup"><span data-stu-id="ef81a-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="ef81a-113">In deze gevallen controleren eenvoudige netwerkverbindingsmonitoren de verbindingen met de proxy die correct is, maar een lagere onderzoekswaarde heeft.</span><span class="sxs-lookup"><span data-stu-id="ef81a-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="ef81a-114">Defender for Endpoint ondersteunt geavanceerde HTTP-niveaucontrole via netwerkbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="ef81a-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="ef81a-115">Wanneer deze is ingeschakeld, wordt er een nieuw type gebeurtenis opgedoken waarin de echte doeldomeinnamen worden bekent.</span><span class="sxs-lookup"><span data-stu-id="ef81a-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="ef81a-116">Netwerkbeveiliging gebruiken om de netwerkverbinding achter een firewall te controleren</span><span class="sxs-lookup"><span data-stu-id="ef81a-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="ef81a-117">Het bewaken van de netwerkverbinding achter een doorgestuurde proxy is mogelijk vanwege extra netwerkgebeurtenissen die afkomstig zijn van netwerkbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="ef81a-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="ef81a-118">Als u ze wilt zien op een apparaattijdlijn, schakelt u netwerkbeveiliging in (minimaal in de auditmodus).</span><span class="sxs-lookup"><span data-stu-id="ef81a-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="ef81a-119">Netwerkbeveiliging kan worden beheerd met de volgende modi:</span><span class="sxs-lookup"><span data-stu-id="ef81a-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="ef81a-120">**Blokkeren**</span><span class="sxs-lookup"><span data-stu-id="ef81a-120">**Block**</span></span> <br> <span data-ttu-id="ef81a-121">Gebruikers of apps worden geblokkeerd om verbinding te maken met gevaarlijke domeinen.</span><span class="sxs-lookup"><span data-stu-id="ef81a-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="ef81a-122">U kunt deze activiteit zien in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ef81a-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="ef81a-123">**Controle**</span><span class="sxs-lookup"><span data-stu-id="ef81a-123">**Audit**</span></span> <br> <span data-ttu-id="ef81a-124">Gebruikers of apps worden niet geblokkeerd om verbinding te maken met gevaarlijke domeinen.</span><span class="sxs-lookup"><span data-stu-id="ef81a-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="ef81a-125">U ziet deze activiteit echter nog steeds in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ef81a-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="ef81a-126">Als u netwerkbeveiliging uitstijt, worden gebruikers of apps niet geblokkeerd om verbinding te maken met gevaarlijke domeinen.</span><span class="sxs-lookup"><span data-stu-id="ef81a-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="ef81a-127">U ziet geen netwerkactiviteit in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ef81a-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="ef81a-128">Als u het niet configureert, is netwerkblokkering standaard uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ef81a-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="ef81a-129">Zie Netwerkbeveiliging [inschakelen voor meer informatie.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ef81a-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="ef81a-130">Effect van onderzoek</span><span class="sxs-lookup"><span data-stu-id="ef81a-130">Investigation impact</span></span>
<span data-ttu-id="ef81a-131">Wanneer netwerkbeveiliging is ingeschakeld, ziet u dat op de tijdlijn van een apparaat het IP-adres de proxy blijft vertegenwoordigen, terwijl het echte doeladres wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ef81a-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![Afbeelding van netwerkgebeurtenissen op de tijdlijn van het apparaat](images/atp-proxy-investigation.png)

<span data-ttu-id="ef81a-133">Extra gebeurtenissen die door de netwerkbeveiligingslaag worden geactiveerd, zijn nu beschikbaar om de echte domeinnamen boven water te krijgen, zelfs achter een proxy.</span><span class="sxs-lookup"><span data-stu-id="ef81a-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="ef81a-134">De gegevens van de gebeurtenis:</span><span class="sxs-lookup"><span data-stu-id="ef81a-134">Event's information:</span></span>

![Afbeelding van één netwerkgebeurtenis](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="ef81a-136">Op zoek naar verbindingsgebeurtenissen met behulp van geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="ef81a-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="ef81a-137">Alle nieuwe verbindingsgebeurtenissen zijn beschikbaar waar u ook op kunt jagen door middel van geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="ef81a-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="ef81a-138">Aangezien deze gebeurtenissen verbindingsgebeurtenissen zijn, kunt u deze vinden onder de tabel DeviceNetworkEvents onder het `ConnecionSuccess` actietype.</span><span class="sxs-lookup"><span data-stu-id="ef81a-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="ef81a-139">Met deze eenvoudige query ziet u alle relevante gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="ef81a-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Afbeelding van geavanceerde zoekquery](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="ef81a-141">U kunt ook gebeurtenissen filteren die betrekking hebben op de verbinding met de proxy zelf.</span><span class="sxs-lookup"><span data-stu-id="ef81a-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="ef81a-142">Gebruik de volgende query om de verbindingen met de proxy te filteren:</span><span class="sxs-lookup"><span data-stu-id="ef81a-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="ef81a-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ef81a-143">Related topics</span></span>
- [<span data-ttu-id="ef81a-144">Netwerkbeveiliging toepassen met GP - CSP-beleid</span><span class="sxs-lookup"><span data-stu-id="ef81a-144">Applying network protection with GP - policy CSP</span></span>](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
