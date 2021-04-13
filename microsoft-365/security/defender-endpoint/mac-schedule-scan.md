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
ms.openlocfilehash: ecfae62bdc092a0b2544bf6f6a76dad1e86b8ab4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689591"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Scans plannen met Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Hoewel u op elk moment een bedreigingsscan kunt starten met Microsoft Defender voor Eindpunt, kan uw bedrijf profiteren van geplande of getijdescans. U kunt bijvoorbeeld een scan plannen die aan het begin van elke werkdag of week wordt uitgevoerd. 

## <a name="schedule-a-scan-with-launchd"></a>Een scan plannen met *de start*

U kunt een scanschema maken met behulp van *de* daemon op een macOS-apparaat.

1. In de volgende code ziet u het schema dat u moet gebruiken om een scan te plannen. Open een teksteditor en gebruik dit voorbeeld als handleiding voor uw eigen geplande scanbestand.

    Zie Info [Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) op de officiële apple developer website voor meer informatie over de bestandsindeling *.plist* die hier wordt gebruikt.

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

2. Sla het bestand op *als com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Als u een volledige scan wilt uitvoeren in plaats van een snelle scan, wijzigt u regel 12, om de optie te gebruiken in plaats van (dat wil zeggen) en het bestand op te slaan als `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* in plaats van *com.microsoft.wdav.sched **quick** scan.plist*.

3. Open **Terminal**.
4. Voer de volgende opdrachten in om het bestand te laden:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. De geplande scan wordt uitgevoerd op de datum, tijd en frequentie die u hebt gedefinieerd in uw p-lijst. In het voorbeeld wordt de scan elke vrijdag om 02:00 uur uitgevoerd. 

    De `Weekday` waarde van gebruikt een geheel getal om de vijfde dag van de week of vrijdag aan te `StartCalendarInterval` geven.

 > [!IMPORTANT]
 > Agenten die zijn *uitgevoerd met start,* worden niet uitgevoerd op de geplande tijd terwijl het apparaat in slaapstand staat. Ze worden in plaats daarvan uitgevoerd zodra het apparaat wordt hervat vanuit de slaapstand.
 >
 > Als het apparaat is uitgeschakeld, wordt de scan uitgevoerd op de volgende geplande scantijd.

## <a name="schedule-a-scan-with-intune"></a>Een scan plannen met Intune

U kunt ook scans plannen met Microsoft Intune. Het [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) script dat beschikbaar is bij [Scripts voor Microsoft Defender voor](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) Eindpunt, blijft bestaan wanneer het apparaat wordt hervat vanuit de slaapstand. 

Zie [Shell-scripts gebruiken op macOS-apparaten in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) voor meer gedetailleerde instructies over het gebruik van dit script in uw bedrijf.
