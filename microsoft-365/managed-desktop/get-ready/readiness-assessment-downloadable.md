---
title: Downloadbare gereedheidscontrole
description: Controleert apparaat- en netwerkinstellingen, inclusief vereiste eindpunten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921969"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="cedcf-104">Downloadbare gereedheidscontrole</span><span class="sxs-lookup"><span data-stu-id="cedcf-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="cedcf-105">Als u goed wilt werken met het beheerde bureaublad van Microsoft, moeten apparaten voldoen aan bepaalde vereisten voor hardware en instellingen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="cedcf-106">Bovendien moet elk apparaat belangrijke eindpunten kunnen bereiken.</span><span class="sxs-lookup"><span data-stu-id="cedcf-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="cedcf-107">Download en voer dit hulpprogramma uit om een HTML-rapport te verkrijgen, resultaten te bekijken en vervolgens actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="cedcf-108">U moet het hulpprogramma en de ondersteunende bestanden downloaden en vervolgens handmatig uitvoeren op elk apparaat dat u wilt registreren in het beheerde bureaublad van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cedcf-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="cedcf-109">Bij elke controle wordt een van de drie mogelijke resultaten door het hulpmiddel rapporteren:</span><span class="sxs-lookup"><span data-stu-id="cedcf-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="cedcf-110">Resultaat</span><span class="sxs-lookup"><span data-stu-id="cedcf-110">Result</span></span>  |<span data-ttu-id="cedcf-111">Betekenis</span><span class="sxs-lookup"><span data-stu-id="cedcf-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="cedcf-112">Klaar</span><span class="sxs-lookup"><span data-stu-id="cedcf-112">Ready</span></span>     | <span data-ttu-id="cedcf-113">U hoeft niets te doen voordat u de inschrijving voltooit.</span><span class="sxs-lookup"><span data-stu-id="cedcf-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="cedcf-114">Advies</span><span class="sxs-lookup"><span data-stu-id="cedcf-114">Advisory</span></span>    | <span data-ttu-id="cedcf-115">Volg de stappen in het hulpprogramma voor een optimaal gebruik van de inschrijving en voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cedcf-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="cedcf-116">U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.</span><span class="sxs-lookup"><span data-stu-id="cedcf-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="cedcf-117">Nog niet gereed</span><span class="sxs-lookup"><span data-stu-id="cedcf-117">Not ready</span></span> | <span data-ttu-id="cedcf-118">*De inschrijving mislukt als* u deze problemen niet op kunt lossen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="cedcf-119">Volg de stappen in het hulpprogramma om deze problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="cedcf-120">De controle verkrijgen</span><span class="sxs-lookup"><span data-stu-id="cedcf-120">Obtain the checker</span></span>

<span data-ttu-id="cedcf-121">Download het ZIP-bestand van https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="cedcf-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="cedcf-122">De gebruiker die het hulpprogramma gebruikt, moet lokale beheerdersrechten hebben op het apparaat waarop het programma wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cedcf-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="cedcf-123">Voer het hulpprogramma vervolgens uit door deze stappen te volgen:</span><span class="sxs-lookup"><span data-stu-id="cedcf-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="cedcf-124">Kopieer het gedownloade ZIP-bestand naar elk apparaat dat u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="cedcf-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="cedcf-125">Alle bestanden in de gecomprimeerde download uitpakken.</span><span class="sxs-lookup"><span data-stu-id="cedcf-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="cedcf-126">Voer **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** uit.</span><span class="sxs-lookup"><span data-stu-id="cedcf-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="cedcf-127">Wanneer de vraag van Gebruikerstoegangsbeheer wordt weergegeven, selecteert u **Ja.**</span><span class="sxs-lookup"><span data-stu-id="cedcf-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="cedcf-128">Het hulpprogramma wordt uitgevoerd en er wordt een rapport geopend in uw standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="cedcf-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="cedcf-129">U kunt het ZIP-archief ook downloaden en  uitpakken naar een gedeelde locatie,Microsoft.MMD.DeviceReadinessAssessmentTool.exeelk apparaat openen en lokaal uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="cedcf-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="cedcf-130">Controles</span><span class="sxs-lookup"><span data-stu-id="cedcf-130">Checks</span></span>

<span data-ttu-id="cedcf-131">Met het downloadbare hulpprogramma worden deze apparaat- en netwerkgerelateerde items gecontroleerd:</span><span class="sxs-lookup"><span data-stu-id="cedcf-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="cedcf-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="cedcf-132">Hardware</span></span>

<span data-ttu-id="cedcf-133">Apparaten moeten voldoen aan specifieke hardwarevereisten om met het beheerde bureaublad van Microsoft te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="cedcf-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="cedcf-134">Momenteel kunnen alleen specifieke [goedgekeurde apparaten](../service-description/device-list.md) zich registreren.</span><span class="sxs-lookup"><span data-stu-id="cedcf-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="cedcf-135">Als uw apparaat na een van de controles mislukt, is het niet compatibel met het beheerde bureaublad van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cedcf-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="cedcf-136">Netwerk-eindpunten</span><span class="sxs-lookup"><span data-stu-id="cedcf-136">Network endpoints</span></span>

<span data-ttu-id="cedcf-137">Apparaten hebben veel toegang tot verschillende [belangrijke eindpunten voor](network.md) gebruik met het beheerde bureaublad van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cedcf-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="cedcf-138">Als het hulpprogramma een **niet-gereed** resultaat meldt, bekijkt u het gedetailleerde rapport om erachter te komen welke eindpunten niet bereikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="cedcf-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="cedcf-139">Pas vervolgens uw firewall of andere netwerkinstellingen aan om ervoor te zorgen dat deze eindpunten bereikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="cedcf-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="cedcf-140">Overige instellingen</span><span class="sxs-lookup"><span data-stu-id="cedcf-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="cedcf-141">Wi-Fi-profielen voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="cedcf-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="cedcf-142">Een **adviesresultaat** betekent dat u gebruik maakt van een aantal Wi-Fi-profielen die certificaten en profielen nodig hebben om goed te werken.</span><span class="sxs-lookup"><span data-stu-id="cedcf-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="cedcf-143">Zie Certificaten en een [Wi-Fi-/VPN-profiel implementeren voor meer informatie.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="cedcf-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="cedcf-144">LAN-profielen</span><span class="sxs-lookup"><span data-stu-id="cedcf-144">LAN profiles</span></span>

<span data-ttu-id="cedcf-145">Een **adviesresultaat** betekent dat u lans hebt die certificaten en profielen nodig hebben om goed te werken.</span><span class="sxs-lookup"><span data-stu-id="cedcf-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="cedcf-146">Zie Certificaten en netwerkprofielen voorbereiden voor beheerd bureaublad [van Microsoft voor meer informatie.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="cedcf-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="cedcf-147">VPN-profielen</span><span class="sxs-lookup"><span data-stu-id="cedcf-147">VPN profiles</span></span>

<span data-ttu-id="cedcf-148">Een **adviesresultaat** betekent dat u een VPN (Virtual Private Network) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="cedcf-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="cedcf-149">Maak een VPN-profiel voor het implementeren van certificaten die zijn geïntegreerd met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cedcf-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="cedcf-150">Zie Certificaten en netwerkprofielen voorbereiden voor beheerd bureaublad [van Microsoft voor meer informatie.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="cedcf-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="cedcf-151">Kaartstations</span><span class="sxs-lookup"><span data-stu-id="cedcf-151">Mapped drives</span></span>

<span data-ttu-id="cedcf-152">Een **adviesresultaat** betekent dat u een aantal kaartstations hebt, die niet worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="cedcf-153">Zie Kaartstations voorbereiden voor Microsoft Managed Desktop voor [meer informatie.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="cedcf-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="cedcf-154">Wachtrijen afdrukken</span><span class="sxs-lookup"><span data-stu-id="cedcf-154">Print queues</span></span>

<span data-ttu-id="cedcf-155">Een **adviesresultaat** betekent dat u een aantal openstaande afdrukwachtrijen hebt, die niet worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="cedcf-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="cedcf-156">Eén oplossing is het gebruik van afdrukken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="cedcf-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="cedcf-157">Zie Afdrukresources [voorbereiden voor het beheerde bureaublad van Microsoft voor meer informatie.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="cedcf-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="cedcf-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="cedcf-158">Proxies</span></span>

<span data-ttu-id="cedcf-159">Een **adviesresultaat** betekent dat er een proxyserver in gebruik is.</span><span class="sxs-lookup"><span data-stu-id="cedcf-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="cedcf-160">Zie Netwerkconfiguratie voor Microsoft Managed Desktop voor [meer informatie.](network.md)</span><span class="sxs-lookup"><span data-stu-id="cedcf-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

