---
title: Prestatieproblemen oplossen voor Microsoft Defender ATP voor Linux
description: Problemen met de prestaties in Microsoft Defender ATP voor Linux oplossen.
keywords: microsoft, defender, atp, linux, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dea52da1952c3fbde8951457caf44232e9d258b7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187731"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="63224-104">Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="63224-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63224-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="63224-105">**Applies to:**</span></span>
- [<span data-ttu-id="63224-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="63224-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="63224-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63224-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="63224-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="63224-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="63224-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="63224-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="63224-110">Dit artikel bevat enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met Betrekking tot Defender voor Eindpunt voor Linux te beperken.</span><span class="sxs-lookup"><span data-stu-id="63224-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="63224-111">Realtimebeveiliging (RTP) is een functie van Defender voor Eindpunt voor Linux die uw apparaat continu bewaakt en beschermt tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="63224-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="63224-112">Het bestaat uit bestands- en procescontrole en andere heuristieken.</span><span class="sxs-lookup"><span data-stu-id="63224-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="63224-113">Afhankelijk van de toepassingen die u gebruikt en uw apparaatkenmerken, kunt u suboptimale prestaties ervaren bij het uitvoeren van Defender voor Eindpunt voor Linux.</span><span class="sxs-lookup"><span data-stu-id="63224-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="63224-114">Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Defender voor Eindpunt voor Linux.</span><span class="sxs-lookup"><span data-stu-id="63224-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="63224-115">Controleer voordat u begint of andere beveiligingsproducten momenteel niet **op het apparaat worden uitgevoerd.**</span><span class="sxs-lookup"><span data-stu-id="63224-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="63224-116">Meerdere beveiligingsproducten kunnen conflicteren en van invloed zijn op de prestaties van de host.</span><span class="sxs-lookup"><span data-stu-id="63224-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="63224-117">De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:</span><span class="sxs-lookup"><span data-stu-id="63224-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="63224-118">Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="63224-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="63224-119">Met deze methode kunt u beperken of Defender voor Eindpunt voor Linux bijdraagt aan de prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="63224-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="63224-120">Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="63224-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="63224-121">Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging door uw beheerder worden uitgeschakeld met de instructies in Voorkeuren instellen voor [Defender voor Eindpunt voor Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="63224-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="63224-122">Als het prestatieprobleem zich blijft voordoen terwijl de realtimebeveiliging is uitgeschakeld, kan de oorzaak van het probleem het eindpuntdetectie- en antwoordonderdeel zijn.</span><span class="sxs-lookup"><span data-stu-id="63224-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="63224-123">Neem in dit geval contact op met de klantondersteuning voor verdere instructies en beperking.</span><span class="sxs-lookup"><span data-stu-id="63224-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="63224-124">Als u de toepassingen wilt vinden die de meeste scans activeren, kunt u realtimestatistieken gebruiken die zijn verzameld door Defender voor Eindpunt voor Linux.</span><span class="sxs-lookup"><span data-stu-id="63224-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63224-125">Deze functie is beschikbaar in versie 100.90.70 of hoger.</span><span class="sxs-lookup"><span data-stu-id="63224-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="63224-126">Deze functie is standaard ingeschakeld op de `Dogfood` kanalen `InsiderFast` en kanalen.</span><span class="sxs-lookup"><span data-stu-id="63224-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="63224-127">Als u een ander updatekanaal gebruikt, kan deze functie worden ingeschakeld vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="63224-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="63224-128">Voor deze functie is realtime beveiliging vereist.</span><span class="sxs-lookup"><span data-stu-id="63224-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="63224-129">Voer de volgende opdracht uit om de status van realtimebeveiliging te controleren:</span><span class="sxs-lookup"><span data-stu-id="63224-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="63224-130">Controleer of de `real_time_protection_enabled` vermelding `true` .</span><span class="sxs-lookup"><span data-stu-id="63224-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="63224-131">Voer anders de volgende opdracht uit om deze in te stellen:</span><span class="sxs-lookup"><span data-stu-id="63224-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="63224-132">Als u huidige statistieken wilt verzamelen, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="63224-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="63224-133">Met ```--output json``` behulp van (let op het dubbele streepje) zorgt u ervoor dat de uitvoernotatie klaar is voor parsing.</span><span class="sxs-lookup"><span data-stu-id="63224-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="63224-134">De uitvoer van deze opdracht toont alle processen en de bijbehorende scanactiviteit.</span><span class="sxs-lookup"><span data-stu-id="63224-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="63224-135">Download op uw Linux-systeem de voorbeeld-Python-parser **high_cpu_parser.py** met de opdracht:</span><span class="sxs-lookup"><span data-stu-id="63224-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="63224-136">De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:</span><span class="sxs-lookup"><span data-stu-id="63224-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="63224-137">Typ vervolgens de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="63224-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="63224-138">De uitvoer van het bovenstaande is een lijst met de belangrijkste bijdragers aan prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="63224-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="63224-139">De eerste kolom is de procesaanduiding (PID), de tweede kolom is de naam van het proces en de laatste kolom is het aantal gescande bestanden, gesorteerd op effect.</span><span class="sxs-lookup"><span data-stu-id="63224-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="63224-140">De uitvoer van de opdracht is bijvoorbeeld iets als de volgende:</span><span class="sxs-lookup"><span data-stu-id="63224-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="63224-141">Als u de prestaties van Defender voor Eindpunt voor Linux wilt verbeteren, zoekt u het getal met het hoogste getal onder de rij en voegt u `Total files scanned` er een uitsluiting voor toe.</span><span class="sxs-lookup"><span data-stu-id="63224-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="63224-142">Zie Uitsluitingen [configureren en valideren voor Defender voor Eindpunt voor Linux voor meer informatie.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="63224-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="63224-143">De toepassing slaat statistieken op in het geheugen en houdt alleen de bestandsactiviteit bij sinds de toepassing is gestart en realtime beveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="63224-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="63224-144">Processen die zijn gestart vóór of tijdens perioden waarin realtimebeveiliging was uitgeschakeld, worden niet meegetelde.</span><span class="sxs-lookup"><span data-stu-id="63224-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="63224-145">Bovendien worden alleen gebeurtenissen geteld die scans hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="63224-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="63224-146">Configureer Microsoft Defender ATP voor Linux met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.</span><span class="sxs-lookup"><span data-stu-id="63224-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="63224-147">Zie Uitsluitingen [configureren en valideren voor Microsoft Defender ATP voor Linux voor meer informatie.](linux-exclusions.md)</span><span class="sxs-lookup"><span data-stu-id="63224-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
