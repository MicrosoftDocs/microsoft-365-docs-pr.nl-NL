---
title: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux
ms.reviewer: ''
description: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, cloud, connectivity, communication
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933107"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>De connectiviteitstest uitvoeren

Als u wilt testen of Defender voor Eindpunt op Linux met de huidige netwerkinstellingen met de cloud kan communiceren, moet u een connectiviteitstest uitvoeren vanaf de opdrachtregel:

```bash
mdatp connectivity test
```

verwachte uitvoer:

```output
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

Als de [verbindingstest](microsoft-defender-endpoint-linux.md#network-connections) mislukt, controleert u of het apparaat internetverbinding heeft en of een van de eindpunten die vereist zijn voor het product, wordt geblokkeerd door een proxy of firewall.

Fouten met krulfout 35 of 60 geven aan dat certificaten zijn geweigerd. Controleer of de verbinding onder SSL- of HTTPS-inspectie valt. Voeg dan Microsoft Defender voor Eindpunt toe aan de lijst toestaan.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Stappen voor probleemoplossing voor omgevingen zonder proxy of met transparante proxy

Als u wilt testen of een verbinding niet is geblokkeerd in een omgeving zonder proxy of met een transparante proxy, moet u de volgende opdracht uitvoeren in de terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

De uitvoer van deze opdracht moet vergelijkbaar zijn met:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Stappen voor probleemoplossing voor omgevingen met statische proxy

> [!WARNING]
> PAC-, WPAD- en geverifieerde proxies worden niet ondersteund. Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.
>
> SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen. Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender for Endpoint op Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie. Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.

Als een statische proxy vereist is, voegt u een proxyparameter toe aan de bovenstaande opdracht, waarbij deze overeenkomt `proxy_address:port` met het proxyadres en de poort:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Zorg ervoor dat u hetzelfde proxyadres en dezelfde poort gebruikt als geconfigureerd in het `/lib/system/system/mdatp.service` bestand. Controleer de proxyconfiguratie als er fouten zijn in de bovenstaande opdrachten.

> [!WARNING]
> De statische proxy kan niet worden geconfigureerd via een omgevingsvariabele voor `HTTPS_PROXY` het hele systeem. Zorg er in plaats daarvan voor `HTTPS_PROXY` dat dit correct is ingesteld in het `/lib/system/system/mdatp.service` bestand.

Als u een statische proxy wilt gebruiken, moet `mdatp.service` het bestand worden gewijzigd. Zorg ervoor dat de `#` voorlijn wordt verwijderd om de volgende regel uit te `/lib/systemd/system/mdatp.service` zetten:

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Zorg er ook voor dat het juiste statische proxyadres wordt ingevuld om deze te `address:port` vervangen.

Als dit bestand juist is, kunt u de volgende opdracht uitvoeren in de terminal om Defender voor Endpoint opnieuw te laden op Linux en de instelling door te geven:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

Probeer bij succes een andere verbindingstest vanaf de opdrachtregel:

```bash
mdatp connectivity test
```

Als het probleem zich blijft voordoen, neem dan contact op met de klantondersteuning.

## <a name="resources"></a>Resources

- Zie Microsoft Defender voor eindpunt configureren voor [statische proxydetectie](linux-static-proxy-configuration.md)voor meer informatie over het configureren van het product voor het gebruik van een statische proxy.
