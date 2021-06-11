---
title: Diagnostische gegevens verzamelen voor naleving en Windows Defender Microsoft Defender Antivirus
description: Een hulpprogramma gebruiken om gegevens te verzamelen om problemen met update compliance op te lossen bij het gebruik van Microsoft Defender Antivirus toevoegen aan evaluatie
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903730"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Diagnostische gegevens voor update compliance verzamelen voor Microsoft Defender Antivirus evaluatie


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u diagnostische gegevens verzamelt die kunnen worden gebruikt door ondersteunings- en technische teams van Microsoft om problemen op te lossen die u mogelijk ondervindt bij het gebruik van de sectie Microsoft Defender Antivirus-evaluatie in de invoeging Update compliance.

Voordat u dit proces probeert, controleert u of u Probleemoplossing Microsoft Defender Antivirus [hebt](troubleshoot-reporting.md)gelezen, aan alle vereisten hebt voldaan en andere voorgestelde stappen voor probleemoplossing hebt genomen.

Op ten minste twee apparaten die niet rapporteren of worden weergegeven in Update compliance, kunt u het diagnostische .cab downloaden door de volgende stappen uit te voeren:

1. Open als volgt een versie op beheerdersniveau van de opdrachtprompt:
        
    a. Open het **menu** Start.

    b. Typ **cmd**. Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **vervolgens Uitvoeren als beheerder.**

    c. Geef beheerdersreferenties op of keur de prompt goed.
        
2. Ga naar de Windows Defender adreslijst. Dit is standaard `C:\Program Files\Windows Defender` .

3. Typ de volgende opdracht en druk op **Enter**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Er .cab een bestand gegenereerd dat verschillende diagnostische logboeken bevat. De locatie van het bestand wordt opgegeven in de uitvoer in de opdrachtprompt. Standaard is de locatie `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Kopieer deze .cab bestanden naar een locatie die kan worden gebruikt door Microsoft-ondersteuning. Een voorbeeld hiervan kan een met een wachtwoord beveiligde map OneDrive die u met ons kunt delen.

6. Verzend een e-mail met behulp van de e-mailsjabloon update <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">complianceondersteuning</a>en vul de sjabloon in met de volgende informatie:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Zie ook

- [Problemen met Windows Defender Microsoft Defender Antivirus rapportage oplossen](troubleshoot-reporting.md)