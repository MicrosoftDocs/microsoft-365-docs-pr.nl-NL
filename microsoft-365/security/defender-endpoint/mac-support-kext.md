---
title: Problemen met kernelextensie oplossen in Microsoft Defender voor Eindpunt voor Mac
description: Problemen met kernelextensie oplossen in Microsoft Defender voor Eindpunt voor Mac.
keywords: microsoft, defender, atp, mac, kernel, extensie
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
ms.openlocfilehash: 877cc619d3ba048cdf6ecc8149f073461d9eac8e
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379506"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a>Problemen met kernelextensie oplossen in Microsoft Defender voor Eindpunt voor Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt voor Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In dit artikel vindt u informatie over het oplossen van problemen met de kernelextensie die is geïnstalleerd als onderdeel van Microsoft Defender voor Eindpunt voor Mac.

Vanaf macOS High Sierra (10.13) moeten alle kernelextensies expliciet worden goedgekeurd voordat ze op het apparaat mogen worden uitgevoerd.

Als u de kernelextensie niet hebt goedgekeurd tijdens de implementatie/installatie van Microsoft Defender voor Eindpunt voor Mac, wordt in de toepassing een banner weergegeven waarin u wordt gevraagd deze in te stellen:

   ![Schermafbeelding van RTP uitgeschakeld](images/mdatp-32-main-app-fix.png)

U kunt ook ```mdatp health``` uitvoeren. Er wordt melding gemaakt als realtimebeveiliging is ingeschakeld, maar niet beschikbaar is. Dit geeft aan dat de kernelextensie niet is goedgekeurd voor gebruik op uw apparaat.

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

In de volgende secties vindt u richtlijnen voor het oplossen van dit probleem, afhankelijk van de methode die u hebt gebruikt om Microsoft Defender voor Eindpunt voor Mac te implementeren.

## <a name="managed-deployment"></a>Beheerde implementatie

Zie de instructies die overeenkomen met het beheerprogramma dat u hebt gebruikt om het product te implementeren:

- [IMPLEMENTATIE OP BASIS VAN JAMF](mac-install-with-jamf.md)
- [Microsoft Intune-implementatie](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a>Handmatige implementatie

Als er minder dan 30 minuten zijn verstreken sinds het product is geïnstalleerd, gaat u naar Systeemvoorkeuren Beveiliging & Privacy, waar u systeemsoftware van ontwikkelaars   >  'Microsoft **Corporation'** moet toestaan. 

Als u deze prompt niet ziet, betekent dit dat er 30 of meer minuten zijn verstreken en dat de kernelextensie nog steeds niet is goedgekeurd voor gebruik op uw apparaat:

![Beveiligings- en privacyvenster na prompt verlopen schermafbeelding](images/mdatp-33-securityprivacysettings-noprompt.png)

In dit geval moet u de volgende stappen uitvoeren om de goedkeuringsstroom opnieuw te activeren.

1. Probeer in Terminal het stuurprogramma te installeren. De volgende bewerking mislukt, omdat de kernelextensie niet is goedgekeurd voor gebruik op het apparaat. De goedkeuringsstroom wordt echter opnieuw in gang flow.

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. Open **Systeemvoorkeuren**  >  **& privacy** in het menu. (Sluit deze eerst, als deze is geopend.)

3. **Systeemsoftware** toestaan van ontwikkelaars "Microsoft Corporation"

4. Installeer het stuurprogramma opnieuw in Terminal. Deze keer slaagt de bewerking:

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    De banner moet verdwijnen uit de Defender-toepassing en moet nu melden dat ```mdatp health``` realtimebeveiliging is ingeschakeld en beschikbaar is:

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
