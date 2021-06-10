---
title: Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux
description: Problemen met de prestaties in Microsoft Defender voor Eindpunt op Linux oplossen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, performance
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
ms.openlocfilehash: 998d8c500613ffa9fc6d790535e555ff9503f590
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281015"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="fef45-104">Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Linux</span><span class="sxs-lookup"><span data-stu-id="fef45-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fef45-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fef45-105">**Applies to:**</span></span>
- [<span data-ttu-id="fef45-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fef45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fef45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fef45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="fef45-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fef45-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fef45-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fef45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fef45-110">In dit artikel vindt u enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met betrekking tot Defender voor Eindpunt op Linux te beperken.</span><span class="sxs-lookup"><span data-stu-id="fef45-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="fef45-111">Realtimebeveiliging (RTP) is een functie van Defender voor Eindpunt op Linux die uw apparaat continu bewaakt en beschermt tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="fef45-111">Real-time protection (RTP) is a feature of Defender for Endpoint on Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="fef45-112">Het bestaat uit bestands- en procescontrole en andere heuristieken.</span><span class="sxs-lookup"><span data-stu-id="fef45-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="fef45-113">Afhankelijk van de toepassingen die u gebruikt en uw apparaatkenmerken, kunt u suboptimale prestaties ervaren bij het uitvoeren van Defender voor Eindpunt op Linux.</span><span class="sxs-lookup"><span data-stu-id="fef45-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint on Linux.</span></span> <span data-ttu-id="fef45-114">Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Defender for Endpoint op Linux.</span><span class="sxs-lookup"><span data-stu-id="fef45-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="fef45-115">Controleer voordat u begint of andere beveiligingsproducten momenteel niet **op het apparaat worden uitgevoerd.**</span><span class="sxs-lookup"><span data-stu-id="fef45-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="fef45-116">Meerdere beveiligingsproducten kunnen conflicteren en van invloed zijn op de prestaties van de host.</span><span class="sxs-lookup"><span data-stu-id="fef45-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="fef45-117">De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:</span><span class="sxs-lookup"><span data-stu-id="fef45-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="fef45-118">Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="fef45-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="fef45-119">Met deze methode kunt u beperken of Defender voor Eindpunt op Linux bijdraagt aan de prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fef45-119">This approach helps narrow down whether Defender for Endpoint on Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="fef45-120">Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="fef45-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="fef45-121">Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging door uw beheerder worden uitgeschakeld met behulp van de instructies in Voorkeuren instellen voor [Defender voor Eindpunt op Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="fef45-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="fef45-122">Als het prestatieprobleem zich blijft voordoen terwijl de realtimebeveiliging is uitgeschakeld, kan de oorzaak van het probleem het eindpuntdetectie en -respons zijn.</span><span class="sxs-lookup"><span data-stu-id="fef45-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="fef45-123">Neem in dit geval contact op met de klantondersteuning voor verdere instructies en beperking.</span><span class="sxs-lookup"><span data-stu-id="fef45-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="fef45-124">Als u de toepassingen wilt vinden die de meeste scans activeren, kunt u realtimestatistieken gebruiken die door Defender voor Eindpunt op Linux zijn verzameld.</span><span class="sxs-lookup"><span data-stu-id="fef45-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef45-125">Deze functie is beschikbaar in versie 100.90.70 of hoger.</span><span class="sxs-lookup"><span data-stu-id="fef45-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="fef45-126">Deze functie is standaard ingeschakeld op de `Dogfood` kanalen `InsiderFast` en kanalen.</span><span class="sxs-lookup"><span data-stu-id="fef45-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="fef45-127">Als u een ander updatekanaal gebruikt, kan deze functie worden ingeschakeld vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="fef45-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="fef45-128">Voor deze functie is realtime beveiliging vereist.</span><span class="sxs-lookup"><span data-stu-id="fef45-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="fef45-129">Voer de volgende opdracht uit om de status van realtimebeveiliging te controleren:</span><span class="sxs-lookup"><span data-stu-id="fef45-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="fef45-130">Controleer of de `real_time_protection_enabled` vermelding `true` .</span><span class="sxs-lookup"><span data-stu-id="fef45-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="fef45-131">Voer anders de volgende opdracht uit om deze in te stellen:</span><span class="sxs-lookup"><span data-stu-id="fef45-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="fef45-132">Als u huidige statistieken wilt verzamelen, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="fef45-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="fef45-133">Met ```--output json``` behulp van (let op het dubbele streepje) zorgt u ervoor dat de uitvoernotatie klaar is voor parsing.</span><span class="sxs-lookup"><span data-stu-id="fef45-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="fef45-134">De uitvoer van deze opdracht toont alle processen en de bijbehorende scanactiviteit.</span><span class="sxs-lookup"><span data-stu-id="fef45-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="fef45-135">Download op uw Linux-systeem de voorbeeld-Python-parser **high_cpu_parser.py** met de opdracht:</span><span class="sxs-lookup"><span data-stu-id="fef45-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="fef45-136">De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:</span><span class="sxs-lookup"><span data-stu-id="fef45-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="fef45-137">Typ vervolgens de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="fef45-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="fef45-138">De uitvoer van het bovenstaande is een lijst met de belangrijkste bijdragers aan prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="fef45-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="fef45-139">De eerste kolom is de procesaanduiding (PID), de tweede kolom is de naam van het proces en de laatste kolom is het aantal gescande bestanden, gesorteerd op effect.</span><span class="sxs-lookup"><span data-stu-id="fef45-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="fef45-140">De uitvoer van de opdracht is bijvoorbeeld iets als de volgende:</span><span class="sxs-lookup"><span data-stu-id="fef45-140">For example, the output of the command will be something like the below:</span></span> 

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

    <span data-ttu-id="fef45-141">Als u de prestaties van Defender voor Eindpunt op Linux wilt verbeteren, zoekt u de versie met het hoogste getal onder de rij en voegt u een `Total files scanned` uitsluiting toe.</span><span class="sxs-lookup"><span data-stu-id="fef45-141">To improve the performance of Defender for Endpoint on Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="fef45-142">Zie Uitsluitingen [configureren en valideren](linux-exclusions.md)voor Defender voor Eindpunt op Linux voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fef45-142">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="fef45-143">De toepassing slaat statistieken op in het geheugen en houdt alleen de bestandsactiviteit bij sinds de toepassing is gestart en realtime beveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="fef45-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="fef45-144">Processen die zijn gestart vóór of tijdens perioden waarin realtimebeveiliging was uitgeschakeld, worden niet meegetelde.</span><span class="sxs-lookup"><span data-stu-id="fef45-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="fef45-145">Bovendien worden alleen gebeurtenissen geteld die scans hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="fef45-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="fef45-146">Configureer Microsoft Defender voor Eindpunt op Linux met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.</span><span class="sxs-lookup"><span data-stu-id="fef45-146">Configure Microsoft Defender for Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="fef45-147">Zie Uitsluitingen [configureren en valideren](linux-exclusions.md)voor Microsoft Defender voor Eindpunt op Linux voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="fef45-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fef45-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fef45-148">See also</span></span>
- [<span data-ttu-id="fef45-149">Statusproblemen van agent onderzoeken</span><span class="sxs-lookup"><span data-stu-id="fef45-149">Investigate agent health issues</span></span>](health-status.md)