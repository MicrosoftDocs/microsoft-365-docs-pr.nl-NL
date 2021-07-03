---
title: Apparaatdetectie configureren
description: Informatie over het configureren van apparaatdetectie in Microsoft 365 Defender met basis- of standaarddetectie
keywords: basis, standaard, eindpuntdetectie configureren, apparaatdetectie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ee56ed2949ea72771d8f08570d4352dbe7548d52
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286943"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="f92c4-104">Apparaatdetectie configureren</span><span class="sxs-lookup"><span data-stu-id="f92c4-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f92c4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f92c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="f92c4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f92c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f92c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f92c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f92c4-108">Detectie kan worden geconfigureerd in de standaard- of basismodus.</span><span class="sxs-lookup"><span data-stu-id="f92c4-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="f92c4-109">Gebruik de standaardoptie om apparaten in uw netwerk actief te zoeken, waardoor de detectie van eindpunten beter wordt gegarandeerd en de apparaatclassificatie uitgebreider is.</span><span class="sxs-lookup"><span data-stu-id="f92c4-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="f92c4-110">U kunt de lijst met apparaten aanpassen die worden gebruikt om standaarddetectie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f92c4-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="f92c4-111">U kunt standaarddetectie inschakelen op alle onboarded-apparaten die deze mogelijkheid ook ondersteunen (momenteel alleen Windows 10-apparaten) of een subset of subset van uw apparaten selecteren door hun apparaatlabels op te geven.</span><span class="sxs-lookup"><span data-stu-id="f92c4-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f92c4-112">Voor een voorbeeld moet u eerst de preview-functies in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f92c4-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="f92c4-113">Vervolgens hebt u toegang tot de configuratie voor apparaatdetectie in Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f92c4-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="f92c4-114">De lijst met niet-beheerde apparaten en beveiligingsaanbevelingen is beschikbaar in zowel Microsoft Defender-beveiligingscentrum als Microsoft 365 beveiligingscentrum, terwijl de dashboardtegels alleen beschikbaar zijn in Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f92c4-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="f92c4-115">Volg de volgende configuratiestappen in Microsoft 365 beveiligingscentrum:</span><span class="sxs-lookup"><span data-stu-id="f92c4-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="f92c4-116">Navigeer **naar Instellingen > apparaatdetectie**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="f92c4-117">Selecteer de detectiemodus die u wilt gebruiken op uw onboarded-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f92c4-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="f92c4-118">Als u hebt geselecteerd om standaarddetectie te gebruiken, selecteert u welke apparaten u wilt gebruiken voor actieve detectie: alle apparaten of op een subset door de apparaatlabels op te geven.</span><span class="sxs-lookup"><span data-stu-id="f92c4-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="f92c4-119">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="f92c4-120">Apparaten uitsluiten van actief worden onderzocht in standaarddetectie</span><span class="sxs-lookup"><span data-stu-id="f92c4-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="f92c4-121">Als er apparaten in uw netwerk zijn die niet actief moeten worden gescand (bijvoorbeeld apparaten die worden gebruikt als honeypots voor een ander beveiligingsprogramma), kunt u ook een lijst met uitsluitingen definiëren om te voorkomen dat ze worden gescand.</span><span class="sxs-lookup"><span data-stu-id="f92c4-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="f92c4-122">Houd er rekening mee dat apparaten nog steeds kunnen worden gevonden met de basisdetectiemodus.</span><span class="sxs-lookup"><span data-stu-id="f92c4-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="f92c4-123">Deze apparaten worden passief ontdekt, maar worden niet actief onderzocht.</span><span class="sxs-lookup"><span data-stu-id="f92c4-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="f92c4-124">Netwerken selecteren die u wilt controleren</span><span class="sxs-lookup"><span data-stu-id="f92c4-124">Select networks to monitor</span></span>

 <span data-ttu-id="f92c4-125">Microsoft Defender voor Eindpunt analyseert een netwerk en bepaalt of het een bedrijfsnetwerk is dat moet worden gecontroleerd of een niet-bedrijfsnetwerk dat kan worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="f92c4-126">Bedrijfsnetwerken worden meestal gekozen om te worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="f92c4-127">U kunt deze beslissing echter overschrijven door ervoor te kiezen niet-bedrijfsnetwerken te controleren waar onboarded-apparaten worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="f92c4-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="f92c4-128">U kunt configureren waar apparaatdetectie kan worden uitgevoerd door op te geven welke netwerken moeten worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="f92c4-129">Wanneer een netwerk wordt gecontroleerd, kan apparaatdetectie op het netwerk worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="f92c4-130">Een lijst met netwerken waarop apparaatdetectie kan worden uitgevoerd, wordt weergegeven op de pagina **Bewaakte netwerken.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="f92c4-131">Alleen top 50-netwerken (afhankelijk van het aantal gekoppelde apparaten) zijn beschikbaar in de netwerklijst.</span><span class="sxs-lookup"><span data-stu-id="f92c4-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="f92c4-132">De lijst met bewaakte netwerken wordt gesorteerd op basis van het totale aantal apparaten dat in de afgelopen 7 dagen op het netwerk is gezien.</span><span class="sxs-lookup"><span data-stu-id="f92c4-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="f92c4-133">U kunt een filter toepassen om een van de volgende detectie-staten van het netwerk te bekijken:</span><span class="sxs-lookup"><span data-stu-id="f92c4-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="f92c4-134">**Bewaakte netwerken:** netwerken waar apparaatdetectie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="f92c4-135">**Genegeerde netwerken:** dit netwerk wordt genegeerd en apparaatdetectie wordt niet uitgevoerd op het netwerk.</span><span class="sxs-lookup"><span data-stu-id="f92c4-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="f92c4-136">**Alles:** zowel bewaakte als genegeerde netwerken worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f92c4-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="f92c4-137">De status van de netwerkmonitor configureren</span><span class="sxs-lookup"><span data-stu-id="f92c4-137">Configure the network monitor state</span></span>

<span data-ttu-id="f92c4-138">U kunt bepalen waar apparaatdetectie plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-138">You control where device discovery takes place.</span></span> <span data-ttu-id="f92c4-139">Bewaakte netwerken is de plaats waar apparaatdetectie wordt uitgevoerd en meestal bedrijfsnetwerken zijn.</span><span class="sxs-lookup"><span data-stu-id="f92c4-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="f92c4-140">U kunt er ook voor kiezen om netwerken te negeren of de eerste detectieclassificatie te selecteren nadat u een status hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="f92c4-141">Als u de eerste detectieclassificatie kiest, wordt de standaardinstelling voor netwerkmonitoren van het systeem toegepast.</span><span class="sxs-lookup"><span data-stu-id="f92c4-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="f92c4-142">Als u de standaardtoestand voor netwerkmonitoren van het systeem selecteert, worden netwerken die zijn geïdentificeerd als zakelijk, gecontroleerd en die zijn geïdentificeerd als niet-bedrijfsnetwerken, automatisch genegeerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="f92c4-143">Selecteer **Instellingen > apparaatdetectie**.</span><span class="sxs-lookup"><span data-stu-id="f92c4-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="f92c4-144">Selecteer **Bewaakte netwerken.**</span><span class="sxs-lookup"><span data-stu-id="f92c4-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="f92c4-145">Bekijk de lijst met netwerken.</span><span class="sxs-lookup"><span data-stu-id="f92c4-145">View the list of networks.</span></span>
4. <span data-ttu-id="f92c4-146">Selecteer de drie puntjes naast de netwerknaam.</span><span class="sxs-lookup"><span data-stu-id="f92c4-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="f92c4-147">Kies of u de oorspronkelijke detectieclassificatie wilt controleren, negeren of gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f92c4-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="f92c4-148">Als u ervoor kiest om een netwerk te controleren dat niet is geïdentificeerd door Microsoft Defender voor Eindpunt als een bedrijfsnetwerk, kan apparaatdetectie buiten uw bedrijfsnetwerk worden veroorzaakt en kunnen daarom thuis- of andere niet-zakelijke apparaten worden gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="f92c4-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="f92c4-149">Als u ervoor kiest om een netwerk te negeren, wordt het controleren en ontdekken van apparaten in dat netwerk gestopt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="f92c4-150">Apparaten die al zijn gevonden, worden niet uit de voorraad verwijderd, maar worden niet meer bijgewerkt en details worden bewaard totdat de bewaarperiode voor gegevens van het Defender for Endpoint verloopt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="f92c4-151">Voordat u ervoor kiest om netwerken van niet-zakelijke ondernemingen te controleren, moet u ervoor zorgen dat u daarvoor toestemming hebt.</span><span class="sxs-lookup"><span data-stu-id="f92c4-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="f92c4-152">Bevestig dat u de wijziging wilt maken.</span><span class="sxs-lookup"><span data-stu-id="f92c4-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="f92c4-153">Apparaten in het netwerk verkennen</span><span class="sxs-lookup"><span data-stu-id="f92c4-153">Explore devices in the network</span></span>

<span data-ttu-id="f92c4-154">U kunt de volgende geavanceerde zoekquery gebruiken om meer context te krijgen over elke netwerknaam die wordt beschreven in de lijst met netwerken.</span><span class="sxs-lookup"><span data-stu-id="f92c4-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="f92c4-155">De query bevat alle onboarded-apparaten die in de afgelopen 7 dagen zijn verbonden met een bepaald netwerk.</span><span class="sxs-lookup"><span data-stu-id="f92c4-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="f92c4-156">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f92c4-156">See also</span></span>

- [<span data-ttu-id="f92c4-157">Overzicht van apparaatdetectie</span><span class="sxs-lookup"><span data-stu-id="f92c4-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="f92c4-158">Veelgestelde vragen over apparaatdetectie</span><span class="sxs-lookup"><span data-stu-id="f92c4-158">Device discovery FAQs</span></span>](device-discovery-faq.md)
