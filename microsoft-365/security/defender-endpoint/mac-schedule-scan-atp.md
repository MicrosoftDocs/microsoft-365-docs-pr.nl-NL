---
title: Scans plannen met MDATP voor macOS
description: Meer informatie over het plannen van een automatische scantijd voor Microsoft Defender ATP in macOS om de activa van uw organisatie beter te beschermen.
keywords: microsoft, defender, atp, mac, scans, antivirus
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
ms.openlocfilehash: 4151513874d295e3033b1ed365f10fb576c4ac18
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059478"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="720d2-104">Scans plannen met Microsoft Defender voor Eindpunt voor Mac</span><span class="sxs-lookup"><span data-stu-id="720d2-104">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="720d2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="720d2-105">**Applies to:**</span></span>
- [<span data-ttu-id="720d2-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="720d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="720d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="720d2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="720d2-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="720d2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="720d2-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="720d2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="720d2-110">Hoewel u op elk moment een bedreigingsscan kunt starten met Microsoft Defender voor Eindpunt, kan uw bedrijf profiteren van geplande of getijdescans.</span><span class="sxs-lookup"><span data-stu-id="720d2-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="720d2-111">U kunt bijvoorbeeld een scan plannen die aan het begin van elke werkdag of week wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="720d2-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="720d2-112">Een scan plannen met *de start*</span><span class="sxs-lookup"><span data-stu-id="720d2-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="720d2-113">U kunt een scanschema maken met behulp van *de* daemon op een macOS-apparaat.</span><span class="sxs-lookup"><span data-stu-id="720d2-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="720d2-114">In de volgende code ziet u het schema dat u moet gebruiken om een scan te plannen.</span><span class="sxs-lookup"><span data-stu-id="720d2-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="720d2-115">Open een teksteditor en gebruik dit voorbeeld als handleiding voor uw eigen geplande scanbestand.</span><span class="sxs-lookup"><span data-stu-id="720d2-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="720d2-116">Zie Info [Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) op de officiële apple developer website voor meer informatie over de bestandsindeling *.plist* die hier wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="720d2-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="720d2-117">Sla het bestand op *als com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="720d2-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="720d2-118">Als u een volledige scan wilt uitvoeren in plaats van een snelle scan, wijzigt u regel 12, om de optie te gebruiken in plaats van (dat wil zeggen) en het bestand op te slaan als `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* in plaats van *com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="720d2-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="720d2-119">Open **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="720d2-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="720d2-120">Voer de volgende opdrachten in om het bestand te laden:</span><span class="sxs-lookup"><span data-stu-id="720d2-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="720d2-121">De geplande scan wordt uitgevoerd op de datum, tijd en frequentie die u hebt gedefinieerd in uw p-lijst.</span><span class="sxs-lookup"><span data-stu-id="720d2-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="720d2-122">In het voorbeeld wordt de scan elke vrijdag om 02:00 uur uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="720d2-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="720d2-123">De `Weekday` waarde van gebruikt een geheel getal om de vijfde dag van de week of vrijdag aan te `StartCalendarInterval` geven.</span><span class="sxs-lookup"><span data-stu-id="720d2-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="720d2-124">Agenten die zijn *uitgevoerd met start,* worden niet uitgevoerd op de geplande tijd terwijl het apparaat in slaapstand staat.</span><span class="sxs-lookup"><span data-stu-id="720d2-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="720d2-125">Ze worden in plaats daarvan uitgevoerd zodra het apparaat wordt hervat vanuit de slaapstand.</span><span class="sxs-lookup"><span data-stu-id="720d2-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="720d2-126">Als het apparaat is uitgeschakeld, wordt de scan uitgevoerd op de volgende geplande scantijd.</span><span class="sxs-lookup"><span data-stu-id="720d2-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="720d2-127">Een scan plannen met Intune</span><span class="sxs-lookup"><span data-stu-id="720d2-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="720d2-128">U kunt ook scans plannen met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="720d2-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="720d2-129">Het [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) script dat beschikbaar is bij [Scripts voor Microsoft Defender voor](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) Eindpunt, blijft bestaan wanneer het apparaat wordt hervat vanuit de slaapstand.</span><span class="sxs-lookup"><span data-stu-id="720d2-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="720d2-130">Zie [Shell-scripts gebruiken op macOS-apparaten in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) voor meer gedetailleerde instructies over het gebruik van dit script in uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="720d2-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
