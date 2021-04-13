---
title: Diagnostische gegevens verzamelen voor Update Compliance en Windows Defender Microsoft Defender Antivirus
description: Een hulpprogramma gebruiken om gegevens te verzamelen om problemen met update compliance op te lossen bij het gebruik van de microsoft Defender Antivirus Assessment add in
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3975a18c2986ac7766664194a6d4b80ee1a503b1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690485"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Diagnostische gegevens voor update compliance verzamelen voor Microsoft Defender AV Assessment

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u diagnostische gegevens verzamelt die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen die u mogelijk ondervindt bij het gebruik van de sectie Microsoft Defender AV-evaluatie in de invoeging Update compliance.

Voordat u dit proces probeert, controleert u of u Problemen met [Microsoft Defender Antivirusrapportage](troubleshoot-reporting.md)oplossen hebt gelezen, aan alle vereisten hebt voldaan en andere voorgestelde stappen voor probleemoplossing hebt genomen.

Op ten minste twee apparaten die niet rapporteren of worden weergegeven in Update Compliance, verkrijgt u het diagnostische .cab-bestand door de volgende stappen uit te voeren:

1. Open als volgt een versie op beheerdersniveau van de opdrachtprompt:
        
    a. Open het **menu** Start.

    b. Typ **cmd**. Klik met de rechtermuisknop op **Opdrachtprompt** en klik **op Uitvoeren als beheerder.**

    c. Voer beheerdersreferenties in of keur de prompt goed.
        
2. Ga naar de Windows Defender-adreslijst. Dit is standaard `C:\Program Files\Windows Defender` .

3. Typ de volgende opdracht en druk op **Enter**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Er wordt een CAB-bestand gegenereerd dat verschillende diagnostische logboeken bevat. De locatie van het bestand wordt opgegeven in de uitvoer in de opdrachtprompt. Standaard is de locatie `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Kopieer deze CAB-bestanden naar een locatie die kan worden gebruikt door Microsoft-ondersteuning. Een voorbeeld hiervan kan een met een wachtwoord beveiligde OneDrive-map zijn die u met ons kunt delen.

6. Verzend een e-mail <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">met</a>behulp van de e-mailsjabloon Ondersteuning bijwerken en vul de sjabloon in met de volgende informatie:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Zie ook

- [Problemen met Windows Defender Microsoft Defender Antivirusrapportage oplossen](troubleshoot-reporting.md)