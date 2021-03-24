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
ms.openlocfilehash: 5c64d16e0753fa87713f2a34583825234fb9c98c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057505"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt voor Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dit artikel bevat enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met Betrekking tot Defender voor Eindpunt voor Linux te beperken.

Realtimebeveiliging (RTP) is een functie van Defender voor Eindpunt voor Linux die uw apparaat continu bewaakt en beschermt tegen bedreigingen. Het bestaat uit bestands- en procescontrole en andere heuristieken.

Afhankelijk van de toepassingen die u gebruikt en uw apparaatkenmerken, kunt u suboptimale prestaties ervaren bij het uitvoeren van Defender voor Eindpunt voor Linux. Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Defender voor Eindpunt voor Linux.

Controleer voordat u begint of andere beveiligingsproducten momenteel niet **op het apparaat worden uitgevoerd.** Meerdere beveiligingsproducten kunnen conflicteren en van invloed zijn op de prestaties van de host.

De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:

1. Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren. Met deze methode kunt u beperken of Defender voor Eindpunt voor Linux bijdraagt aan de prestatieproblemen.

    Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld vanaf de opdrachtregel:

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging door uw beheerder worden uitgeschakeld met de instructies in Voorkeuren instellen voor [Defender voor Eindpunt voor Linux.](linux-preferences.md)

    Als het prestatieprobleem zich blijft voordoen terwijl de realtimebeveiliging is uitgeschakeld, kan de oorzaak van het probleem het eindpuntdetectie- en antwoordonderdeel zijn. Neem in dit geval contact op met de klantondersteuning voor verdere instructies en beperking.

2. Als u de toepassingen wilt vinden die de meeste scans activeren, kunt u realtimestatistieken gebruiken die zijn verzameld door Defender voor Eindpunt voor Linux.

    > [!NOTE]
    > Deze functie is beschikbaar in versie 100.90.70 of hoger.

    Deze functie is standaard ingeschakeld op de `Dogfood` kanalen `InsiderFast` en kanalen. Als u een ander updatekanaal gebruikt, kan deze functie worden ingeschakeld vanaf de opdrachtregel:
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    Voor deze functie is realtime beveiliging vereist. Voer de volgende opdracht uit om de status van realtimebeveiliging te controleren:

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    Controleer of de `real_time_protection_enabled` vermelding `true` . Voer anders de volgende opdracht uit om deze in te stellen:

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    Als u huidige statistieken wilt verzamelen, gaat u als volgende te werk:

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > Met ```--output json``` behulp van (let op het dubbele streepje) zorgt u ervoor dat de uitvoernotatie klaar is voor parsing.

    De uitvoer van deze opdracht toont alle processen en de bijbehorende scanactiviteit.

3. Download op uw Linux-systeem de voorbeeld-Python-parser **high_cpu_parser.py** met de opdracht:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. Typ vervolgens de volgende opdrachten:

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      De uitvoer van het bovenstaande is een lijst met de belangrijkste bijdragers aan prestatieproblemen. De eerste kolom is de procesaanduiding (PID), de tweede kolom is de naam van het proces en de laatste kolom is het aantal gescande bestanden, gesorteerd op effect.
    De uitvoer van de opdracht is bijvoorbeeld iets als de volgende: 

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

    Als u de prestaties van Defender voor Eindpunt voor Linux wilt verbeteren, zoekt u het getal met het hoogste getal onder de rij en voegt u `Total files scanned` er een uitsluiting voor toe. Zie Uitsluitingen [configureren en valideren voor Defender voor Eindpunt voor Linux voor meer informatie.](linux-exclusions.md)

    >[!NOTE]
    > De toepassing slaat statistieken op in het geheugen en houdt alleen de bestandsactiviteit bij sinds de toepassing is gestart en realtime beveiliging is ingeschakeld. Processen die zijn gestart vóór of tijdens perioden waarin realtimebeveiliging was uitgeschakeld, worden niet meegetelde. Bovendien worden alleen gebeurtenissen geteld die scans hebben geactiveerd.

5. Configureer Microsoft Defender ATP voor Linux met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.

    Zie Uitsluitingen [configureren en valideren voor Microsoft Defender ATP voor Linux voor meer informatie.](linux-exclusions.md)
