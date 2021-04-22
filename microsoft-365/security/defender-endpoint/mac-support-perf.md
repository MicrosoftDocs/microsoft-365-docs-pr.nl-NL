---
title: Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt in macOS
description: Problemen met de prestaties oplossen in Microsoft Defender voor Eindpunt in macOS.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 623717e7b1a3149dbccf07d32200820a7f9083cb
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934247"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="d2f6f-104">Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt in macOS</span><span class="sxs-lookup"><span data-stu-id="d2f6f-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2f6f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d2f6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2f6f-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="d2f6f-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="d2f6f-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d2f6f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2f6f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2f6f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d2f6f-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d2f6f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d2f6f-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d2f6f-111">Dit onderwerp bevat enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met betrekking tot Microsoft Defender voor Eindpunt op macOS te beperken.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="d2f6f-112">Realtimebeveiliging (RTP) is een functie van Microsoft Defender voor Eindpunt op macOS die uw apparaat continu bewaakt en beschermt tegen bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="d2f6f-113">Het bestaat uit bestands- en procescontrole en andere heuristieken.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="d2f6f-114">Afhankelijk van de toepassingen die u gebruikt en de kenmerken van uw apparaat, kunt u suboptimale prestaties ervaren bij het uitvoeren van Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="d2f6f-115">Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Microsoft Defender voor Eindpunt op macOS.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="d2f6f-116">De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="d2f6f-117">Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="d2f6f-118">Met deze methode kunt u beperken of Microsoft Defender voor Eindpunt voor macOS bijdraagt aan de prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="d2f6f-119">Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld met behulp van een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="d2f6f-120">Vanuit de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-120">From the user interface.</span></span> <span data-ttu-id="d2f6f-121">Open Microsoft Defender voor Eindpunt in macOS en ga naar **Instellingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="d2f6f-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![Schermopname van realtimebeveiliging beheren](images/mdatp-36-rtp.png)

    - <span data-ttu-id="d2f6f-123">Vanuit de Terminal.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-123">From the Terminal.</span></span> <span data-ttu-id="d2f6f-124">Voor beveiligingsdoeleinden is voor deze bewerking hoogte vereist.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="d2f6f-125">Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging door uw beheerder worden uitgeschakeld met behulp van de instructies in Voorkeuren instellen voor [Microsoft Defender voor Eindpunt op macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="d2f6f-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="d2f6f-126">Als het prestatieprobleem zich blijft voordoen terwijl de realtimebeveiliging is uitgeschakeld, kan de oorzaak van het probleem het eindpuntdetectie- en antwoordonderdeel zijn.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="d2f6f-127">Neem in dit geval contact op met de klantondersteuning voor meer instructies en risicobeperking.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="d2f6f-128">Open Finder en navigeer naar **Applications**  >  **Utilities.**</span><span class="sxs-lookup"><span data-stu-id="d2f6f-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="d2f6f-129">Open **Activiteitsmonitor** en analyseer welke toepassingen de resources op uw systeem gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="d2f6f-130">Voorbeelden hiervan zijn software-updaters en compilers.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="d2f6f-131">Als u de toepassingen wilt vinden die de meeste scans activeren, kunt u realtimestatistieken gebruiken die zijn verzameld door Defender voor Eindpunt op Mac.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2f6f-132">Deze functie is beschikbaar in versie 100.90.70 of hoger.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="d2f6f-133">Deze functie is standaard ingeschakeld op de **kanalen Dogfood** en **InsiderFast.**</span><span class="sxs-lookup"><span data-stu-id="d2f6f-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="d2f6f-134">Als u een ander updatekanaal gebruikt, kan deze functie worden ingeschakeld vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="d2f6f-135">Voor deze functie is realtime beveiliging vereist.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="d2f6f-136">Voer de volgende opdracht uit om de status van realtimebeveiliging te controleren:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="d2f6f-137">Controleer of de **real_time_protection_enabled** waar is.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="d2f6f-138">Voer anders de volgende opdracht uit om deze in te stellen:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="d2f6f-139">Als u huidige statistieken wilt verzamelen, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > <span data-ttu-id="d2f6f-140">Met **--output json** (let op het dubbele streepje) zorgt u ervoor dat de uitvoernotatie klaar is voor parsing.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="d2f6f-141">De uitvoer van deze opdracht toont alle processen en de bijbehorende scanactiviteit.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="d2f6f-142">Download op uw Mac-systeem de voorbeeld-Python-parser high_cpu_parser.py met de opdracht:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="d2f6f-143">De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="d2f6f-144">Typ vervolgens de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="d2f6f-145">De uitvoer van het bovenstaande is een lijst met de belangrijkste bijdragers aan prestatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="d2f6f-146">De eerste kolom is de procesaanduiding (PID), de tweede kolom is de naam van het proces en de laatste kolom is het aantal gescande bestanden, gesorteerd op effect.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="d2f6f-147">De uitvoer van de opdracht is bijvoorbeeld iets als de volgende:</span><span class="sxs-lookup"><span data-stu-id="d2f6f-147">For example, the output of the command will be something like the below:</span></span>

      ```output
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

      <span data-ttu-id="d2f6f-148">Als u de prestaties van Defender voor Eindpunt op Mac wilt verbeteren, zoekt u de optie met het hoogste getal onder de rij Gescande bestanden totaal en voegt u er een uitsluiting voor toe.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="d2f6f-149">Zie Uitsluitingen [configureren en valideren](linux-exclusions.md)voor Defender voor Eindpunt op Linux voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2f6f-150">De toepassing slaat statistieken op in het geheugen en houdt alleen de bestandsactiviteit bij sinds de toepassing is gestart en realtime beveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="d2f6f-151">Processen die zijn gestart vóór of tijdens perioden waarin realtimebeveiliging was uitgeschakeld, worden niet meegetelde.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="d2f6f-152">Bovendien worden alleen gebeurtenissen geteld die scans hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="d2f6f-153">Configureer Microsoft Defender voor Eindpunt op macOS met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="d2f6f-154">Zie [Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op macOS](mac-exclusions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d2f6f-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
