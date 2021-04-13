---
title: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op macOS
description: In dit onderwerp wordt beschreven hoe u problemen met cloudconnectiviteit voor Microsoft Defender voor Eindpunt op macOS kunt oplossen
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8871274cabae0762cecc2ff513afe93c2d4811f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688499"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Platform** macOS

In dit onderwerp wordt beschreven hoe u problemen met cloudconnectiviteit voor Microsoft Defender voor Eindpunt op macOS kunt oplossen.

## <a name="run-the-connectivity-test"></a>De connectiviteitstest uitvoeren
Als u wilt testen of Defender voor Eindpunt voor Mac met de huidige netwerkinstellingen met de cloud kan communiceren, moet u een connectiviteitstest uitvoeren vanaf de opdrachtregel:

```Bash
mdatp connectivity test
```

verwachte uitvoer:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Als de [verbindingstest](microsoft-defender-endpoint-mac.md#network-connections) mislukt, controleert u of het apparaat internetverbinding heeft en of een van de eindpunten die vereist zijn voor het product, wordt geblokkeerd door een proxy of firewall.

Fouten met krulfout 35 of 60 wijzen op afwijzing van certificaatpinning, wat een mogelijk probleem met SSL- of HTTPS-inspectie aangeeft. Zie onderstaande instructies over de configuratie van SSL-inspectie.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Stappen voor probleemoplossing voor omgevingen zonder proxy of met Proxy autoconfig (PAC) of met WPAD (Web Proxy AutoDiscovery Protocol)
Gebruik de volgende procedure om te testen of een verbinding niet is geblokkeerd in een omgeving zonder een proxy of met Proxy autoconfig (PAC) of met WPAD (Web Proxy AutoDiscovery Protocol).

Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.

> [!WARNING]
> Geverifieerde proxies worden niet ondersteund. Zorg ervoor dat alleen PAC, WPAD of een statische proxy wordt gebruikt. SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen. Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Microsoft Defender voor Eindpunt op macOS rechtstreeks door te geven aan de relevante URL's zonder interceptie. Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.
Om te testen of een verbinding niet is geblokkeerd: In een browser zoals Microsoft Edge voor Mac of Safari openen https://x.cp.wd.microsoft.com/api/report en https://cdn.x.cp.wd.microsoft.com/ping .

Voer desgewenst in Terminal de volgende opdracht uit:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

De uitvoer van deze opdracht moet vergelijkbaar zijn met:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
