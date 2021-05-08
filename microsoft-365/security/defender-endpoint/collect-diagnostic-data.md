---
title: Diagnostische gegevens van Microsoft Defender Antivirus
description: Een hulpprogramma gebruiken om gegevens te verzamelen om problemen met Microsoft Defender Antivirus
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender av, groepsbeleidsobject, instelling, diagnostische gegevens
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccf6da0e1bc91a29865868305b5333f7ef9c47cc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274782"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a>Diagnostische gegevens van Microsoft Defender AV verzamelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt beschreven hoe u diagnostische gegevens verzamelt die kunnen worden gebruikt door microsoft-ondersteunings- en technische teams om problemen op te lossen die u mogelijk ondervindt bij het gebruik van microsoft Defender AV.

> [!NOTE]
> Als onderdeel van het onderzoek- of antwoordproces kunt u een onderzoekspakket verzamelen vanaf een apparaat. Dit doet u als: [Onderzoekspakket van apparaten verzamelen.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)

Op ten minste twee apparaten die met hetzelfde probleem te maken hebben, kunt u het .cab diagnostisch bestand verkrijgen door de volgende stappen uit te voeren:

1. Open als volgt een versie op beheerdersniveau van de opdrachtprompt:

    a. Open het **menu** Start.

    b. Typ **cmd**. Klik met de rechtermuisknop op **Opdrachtprompt** en klik **op Uitvoeren als beheerder.**

    c. Voer beheerdersreferenties in of keur de prompt goed.

2. Ga naar de Microsoft Defender-adreslijst. Dit is standaard `C:\Program Files\Windows Defender` .

> [!NOTE]
> Als u een bijgewerkte Versie van [het Microsoft Defender-platform gebruikt,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)kunt u vanaf `MpCmdRun` de volgende locatie uitvoeren: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

3. Typ de volgende opdracht en druk op **Enter**  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. Er .cab een bestand gegenereerd dat verschillende diagnostische logboeken bevat. De locatie van het bestand wordt opgegeven in de uitvoer in de opdrachtprompt. Standaard is de locatie `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

> [!NOTE]
> Als u het cabbestand wilt omleiden naar een ander pad of unc-share, gebruikt u de volgende opdracht: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`  <br/>Zie Diagnostische gegevens [omleiden naar een UNC-share](#redirect-diagnostic-data-to-a-unc-share)voor meer informatie.

5. Kopieer deze .cab bestanden naar een locatie die kan worden gebruikt door Microsoft-ondersteuning. Een voorbeeld hiervan kan een met een wachtwoord beveiligde map OneDrive die u met ons kunt delen.

> [!NOTE]
>Als u een probleem hebt met de <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>naleving bijwerken, verzendt u een e-mail met de e-mailsjabloon Ondersteuning bijwerken en vult u de sjabloon in met de volgende informatie:
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>Diagnostische gegevens omleiden naar een UNC-share
Als u diagnostische gegevens wilt verzamelen in een centrale opslagplaats, kunt u de parameter SupportLogLocation opgeven.

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

Kopieert de diagnostische gegevens naar het opgegeven pad. Als het pad niet is opgegeven, worden de diagnostische gegevens gekopieerd naar de locatie die is opgegeven in de ondersteuningslogboeklocatieconfiguratie.

Wanneer de parameter SupportLogLocation wordt gebruikt, wordt een mapstructuur als volgt gemaakt in het doelpad:

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| veld  | Omschrijving   |
|:----|:----|
| pad | Het pad zoals opgegeven op de opdrachtregel of opgehaald uit configuratie
| MMDD | Maand en dag waarop de diagnostische gegevens zijn verzameld (bijvoorbeeld 0530)
| hostnaam | De hostnaam van het apparaat waarop de diagnostische gegevens zijn verzameld
| HHMM | Uren en minuten waarop de diagnostische gegevens zijn verzameld (bijvoorbeeld 1422)

> [!NOTE]
> Wanneer u een bestands delen gebruikt, moet u ervoor zorgen dat het account dat wordt gebruikt om het diagnostische pakket te verzamelen, schrijftoegang heeft tot de share.  

## <a name="specify-location-where-diagnostic-data-is-created"></a>Locatie opgeven waar diagnostische gegevens worden gemaakt

U kunt ook opgeven waar het diagnostische .cab wordt gemaakt met een groepsbeleidsobject (GPO). 

1. Open de editor voor lokaal groepsbeleid en zoek de OndersteuningLogLocation-GPO op: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`
   
1. Selecteer **Het adreslijstpad definiëren om ondersteuningslogboekbestanden te kopiëren.**

    ![Schermafbeelding van de editor voor lokaal groepsbeleid](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Schermafbeelding van de instelling pad definiëren voor logboekbestanden](images/GPO2-SupportLogLocationGPPage.png)  
3. Selecteer ingeschakeld in de beleidseditor.
       
4. Geef het adreslijstpad op waar u de ondersteuningslogboekbestanden wilt kopiëren in **het veld Opties.**
     ![Schermafbeelding van aangepaste instelling voor ingeschakeld adreslijstpad](images/GPO3-SupportLogLocationGPPageEnabledExample.png) 
5. Selecteer **OK** of **Toepassen.**

## <a name="see-also"></a>Zie ook

- [Problemen met Microsoft Defender Antivirus rapportage oplossen](troubleshoot-reporting.md)