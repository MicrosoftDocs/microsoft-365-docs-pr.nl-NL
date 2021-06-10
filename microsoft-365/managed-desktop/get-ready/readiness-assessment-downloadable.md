---
title: Downloadbare gereedheidsevaluatie-controle
description: Hiermee worden apparaat- en netwerkinstellingen gecontroleerd, inclusief vereiste eindpunten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581032"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="95c89-104">Downloadbare gereedheidsevaluatie-controle</span><span class="sxs-lookup"><span data-stu-id="95c89-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="95c89-105">Als u goed wilt werken met Microsoft Managed Desktop, moeten apparaten voldoen aan bepaalde vereisten voor hardware en instellingen.</span><span class="sxs-lookup"><span data-stu-id="95c89-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="95c89-106">Bovendien moet elk apparaat belangrijke eindpunten kunnen bereiken.</span><span class="sxs-lookup"><span data-stu-id="95c89-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="95c89-107">Download en voer dit hulpprogramma uit om een HTML-rapport te verkrijgen, resultaten weer te geven en actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="95c89-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="95c89-108">U moet het hulpprogramma en de ondersteunende bestanden downloaden en vervolgens handmatig uitvoeren op elk apparaat dat u wilt registreren voor Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="95c89-109">Voor elke controle rapporteert het hulpprogramma een van de drie mogelijke resultaten:</span><span class="sxs-lookup"><span data-stu-id="95c89-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="95c89-110">Resultaat</span><span class="sxs-lookup"><span data-stu-id="95c89-110">Result</span></span>  |<span data-ttu-id="95c89-111">Betekenis</span><span class="sxs-lookup"><span data-stu-id="95c89-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="95c89-112">Gereed</span><span class="sxs-lookup"><span data-stu-id="95c89-112">Ready</span></span>     | <span data-ttu-id="95c89-113">Er is geen actie vereist voordat u de inschrijving voltooit.</span><span class="sxs-lookup"><span data-stu-id="95c89-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="95c89-114">Advies</span><span class="sxs-lookup"><span data-stu-id="95c89-114">Advisory</span></span>    | <span data-ttu-id="95c89-115">Volg de stappen in het hulpprogramma voor de beste ervaring met registratie en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="95c89-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="95c89-116">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="95c89-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="95c89-117">Nog niet klaar</span><span class="sxs-lookup"><span data-stu-id="95c89-117">Not ready</span></span> | <span data-ttu-id="95c89-118">*De inschrijving mislukt als* u deze problemen niet op kunt lossen.</span><span class="sxs-lookup"><span data-stu-id="95c89-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="95c89-119">Volg de stappen in het hulpprogramma om deze op te lossen.</span><span class="sxs-lookup"><span data-stu-id="95c89-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="95c89-120">De controle verkrijgen</span><span class="sxs-lookup"><span data-stu-id="95c89-120">Obtain the checker</span></span>

<span data-ttu-id="95c89-121">Download het .zip bestand van https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="95c89-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="95c89-122">De gebruiker die het hulpprogramma gebruikt, moet de lokale beheerdersrechten hebben op het apparaat waarop de functie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="95c89-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="95c89-123">Voer het hulpprogramma vervolgens uit door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="95c89-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="95c89-124">Kopieer het gedownloade .zip naar elk apparaat dat u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="95c89-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="95c89-125">Haal alle bestanden in de gecomprimeerde download op.</span><span class="sxs-lookup"><span data-stu-id="95c89-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="95c89-126">Voer **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** uit.</span><span class="sxs-lookup"><span data-stu-id="95c89-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="95c89-127">Wanneer de prompt Gebruikerstoegangsbesturingselement wordt weergegeven, selecteert u **Ja**.</span><span class="sxs-lookup"><span data-stu-id="95c89-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="95c89-128">Het hulpprogramma wordt uitgevoerd en opent een rapport in uw standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="95c89-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="95c89-129">U kunt het archief ook downloaden en .zip naar een gedeelde locatie, toegang **tot** Microsoft.MMD.DeviceReadinessAssessmentTool.exeelk apparaat en vervolgens lokaal uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="95c89-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="95c89-130">Controles</span><span class="sxs-lookup"><span data-stu-id="95c89-130">Checks</span></span>

<span data-ttu-id="95c89-131">Met het downloadbare hulpprogramma worden deze apparaat- en netwerkgerelateerde items gecontroleerd:</span><span class="sxs-lookup"><span data-stu-id="95c89-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="95c89-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="95c89-132">Hardware</span></span>

<span data-ttu-id="95c89-133">Apparaten moeten voldoen aan specifieke hardwarevereisten voor gebruik met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="95c89-134">Op dit moment mogen alleen specifieke [goedgekeurde](../service-description/device-list.md) apparaten zich registreren.</span><span class="sxs-lookup"><span data-stu-id="95c89-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="95c89-135">Als uw apparaat een van de controles mislukt, is het niet compatibel met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="95c89-136">Netwerk-eindpunten</span><span class="sxs-lookup"><span data-stu-id="95c89-136">Network endpoints</span></span>

<span data-ttu-id="95c89-137">Apparaten kunnen veel verschillende belangrijke eindpunten [bereiken om](network.md) te werken met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="95c89-138">Als het hulpprogramma  een niet-gereed resultaat rapporteert, bekijkt u het gedetailleerde rapport om erachter te komen welke eindpunten niet bereikbaar waren.</span><span class="sxs-lookup"><span data-stu-id="95c89-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="95c89-139">Pas vervolgens uw firewall of andere netwerkinstellingen aan om ervoor te zorgen dat deze eindpunten kunnen worden bereikt.</span><span class="sxs-lookup"><span data-stu-id="95c89-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="95c89-140">Andere instellingen</span><span class="sxs-lookup"><span data-stu-id="95c89-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="95c89-141">Enterprise Wi-Fi-profielen</span><span class="sxs-lookup"><span data-stu-id="95c89-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="95c89-142">Een **adviesresultaat** betekent dat u bepaalde wi-fi-profielen gebruikt die certificaten en profielen nodig hebben om goed te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="95c89-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="95c89-143">Zie Certificaten en [Wi-Fi/VPN-profiel](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)implementeren voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="95c89-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="95c89-144">LAN-profielen</span><span class="sxs-lookup"><span data-stu-id="95c89-144">LAN profiles</span></span>

<span data-ttu-id="95c89-145">Een **adviesresultaat** betekent dat u LN's hebt die certificaten en profielen nodig hebben om goed te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="95c89-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="95c89-146">Zie Certificaten en netwerkprofielen voorbereiden [voor](certs-wifi-lan.md)Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="95c89-147">VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="95c89-147">VPN profiles</span></span>

<span data-ttu-id="95c89-148">Een **adviesresultaat** betekent dat u een virtueel privénetwerk (VPN) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="95c89-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="95c89-149">Maak een VPN-profiel dat certificaten implementeert die zijn geïntegreerd met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="95c89-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="95c89-150">Zie Certificaten en netwerkprofielen voorbereiden [voor](certs-wifi-lan.md)Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="95c89-151">In kaart gebrachte stations</span><span class="sxs-lookup"><span data-stu-id="95c89-151">Mapped drives</span></span>

<span data-ttu-id="95c89-152">Een **Advisory-resultaat** betekent dat u bepaalde in kaart gebrachte stations hebt, die niet worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="95c89-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="95c89-153">Zie Kaartstations voorbereiden [voor](mapped-drives.md)Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="95c89-154">Wachtrijen afdrukken</span><span class="sxs-lookup"><span data-stu-id="95c89-154">Print queues</span></span>

<span data-ttu-id="95c89-155">Een **adviesresultaat** betekent dat u een aantal openstaande afdrukwachtrijen hebt, die niet worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="95c89-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="95c89-156">Eén oplossing is het gebruik van cloudafdrukken.</span><span class="sxs-lookup"><span data-stu-id="95c89-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="95c89-157">Zie Afdrukresources voorbereiden [voor](printing.md)Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="95c89-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="95c89-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="95c89-158">Proxies</span></span>

<span data-ttu-id="95c89-159">Een **adviesresultaat** betekent dat u een proxyserver in gebruik hebt.</span><span class="sxs-lookup"><span data-stu-id="95c89-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="95c89-160">Zie Netwerkconfiguratie voor [Microsoft Managed Desktop.](network.md)</span><span class="sxs-lookup"><span data-stu-id="95c89-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

