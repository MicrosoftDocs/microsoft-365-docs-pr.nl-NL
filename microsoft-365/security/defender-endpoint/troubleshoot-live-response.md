---
title: Problemen met microsoft Defender ATP live-antwoord oplossen
description: Problemen oplossen die zich kunnen voordoen bij het gebruik van live-antwoorden in Microsoft Defender ATP
keywords: problemen met livereactie, live, antwoord, vergrendeld, bestand oplossen
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 62525548be777a3187cea5ed4be622ac9d42079b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183814"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Problemen met live-antwoorden op Microsoft Defender voor Eindpunt oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Op deze pagina vindt u gedetailleerde stappen om problemen met livereacties op te lossen.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Bestand kan niet worden gebruikt tijdens livereactiesessies
Als u tijdens een livereactiesessie een actie probeert uit te voeren, wordt er een foutbericht weergegeven waarin wordt aangegeven dat het bestand niet kan worden gebruikt, moet u de onderstaande stappen gebruiken om het probleem op te lossen.

1. Kopieer het volgende scriptcodefragment en sla het op als een PS1-bestand:

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. Voeg het script toe aan de live antwoordbibliotheek.
3. Voer het script uit met één parameter: het bestandspad van het bestand dat moet worden gekopieerd.
4. Ga naar de map TEMP.
5. Voer de actie uit die u wilt uitvoeren voor het gekopieerde bestand.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Slow live response sessions or delays during initial connections
Live response maakt gebruik van De registratie van de Defender voor eindpunten-sensor met de WNS-service in Windows. Als u verbindingsproblemen hebt met livereacties, bevestigt u de volgende details:
1. `notify.windows.com` is niet geblokkeerd in uw omgeving. Zie Apparaatproxy- en [internetverbindingsinstellingen configureren](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie.
2. WpnService (Windows Push Notifications System Service) is niet uitgeschakeld.

Raadpleeg de onderstaande artikelen om volledig inzicht te krijgen in het gedrag en de vereisten van de WpnService-service:
- [Overzicht van Windows Push Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Enterprise Firewall en proxyconfiguraties ter ondersteuning van WNS-verkeer](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Openbare IP-bereik (Microsoft Push Notifications Service)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

